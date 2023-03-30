# InfluxDB 作为物联网边缘历史学家:爬行/行走/奔跑方法

> 原文：<https://thenewstack.io/influxdb-as-an-iot-edge-historian-a-crawl-walk-run-approach/>

[](https://www.linkedin.com/in/jrmyers)

 [杰森·迈尔斯

杰森是 InfluxData 的技术营销作家。他获得了芝加哥罗耀拉大学的爱尔兰现代史博士学位。从那以后，他利用自己的写作技巧为一系列初创公司和科技公司创作内容。](https://www.linkedin.com/in/jrmyers) [](https://www.linkedin.com/in/jrmyers)

如何将数据放入数据库是开发人员面临的数据处理的最基本的问题之一。当您处理本地设备时，数据收集可能具有足够的挑战性。从边缘设备添加数据带来了一系列全新的挑战。然而，物联网边缘设备的指数级增长意味着公司需要成熟可靠的方法来收集数据。

以下是从边缘设备收集数据的三种不同方法。边缘设备具有不同的功能—处理能力、内存容量、连接性等。—因此，为您的使用情形找到合适的解决方案可能需要一些反复试验。但是，您可以使用这些方法作为构建解决方案的起点。

对于上下文，我们使用 InfluxDB 作为处理和存储解决方案，InfluxDB 的云版本是这里的目标。这些例子中的每个边缘设备也运行 InfluxDB 的开源版本。我们使用 Flux 语言来创建执行数据转换和注释的任务。

## 爬网:基本存储和转发

这是从边缘设备向 InfluxDB 云数据库获取数据的最基本设置。在这里，原始数据直接从 InfluxDB 的边缘实例写入云实例。

基本存储转发方法的过程如下所示:

1.  在边缘上运行的 InfluxDB 实例中创建一个 bucket。我们将该存储区称为“设备”，并将该数据的保留策略设置为一小时。
2.  在 InfluxDB 的云实例中创建一个 bucket。我们将这个存储区称为“edge_devices ”,并设置了 30 天的保留策略。
3.  在 InfluxDB 中创建一个任务，每一分钟将原始数据从边缘的“devices”桶推送到云中的“edge_devices”桶。
4.  将“edge_host”标记注入到传入的数据中。

### 优势

*   快速且易于设置。
*   几乎不需要边缘计算能力。

### 不足之处

*   增加云实例中不干净数据的数量。
*   边缘数据连接需要更高的吞吐量。

## 行走:向下采样和前进

在这种方法中，来自边缘的原始数据在边缘的内存中被向下采样，并且向下采样的数据被推送到云中，在云中被写入 InfluxDB。

基本存储转发方法的过程如下所示:

1.  在边缘上运行的 InfluxDB 实例中创建一个 bucket。同样，我们将该存储区称为“设备”，并为该数据设置一小时的保留策略。
2.  在 InfluxDB 的云实例中创建一个 bucket。我们将这个存储桶称为“edge_aggregate ”,并将其设置为 30 天保留策略。
3.  在 InfluxDB 的 edge 实例中创建一个任务，该任务对 edge 的“devices”桶中的原始数据进行缩减采样，并每隔一分钟将缩减采样的数据发送到云中的“edge_aggregate”桶。
4.  将“edge_host”标记注入到传入的数据中。

### 优势

*   快速且易于设置。
*   减少发送到云实例的不干净的原始数据量。
*   降低边缘数据连接吞吐量需求。

### 不足之处

*   需要更多的边缘计算能力。
*   需要更多的边缘内存。
*   需要边缘存储。

## 运行:强大的边缘历史记录

在第三个例子中，我们在边缘做了更多的工作。在这里，数据历史学家的角色实际上转移到了边缘，因为 InfluxDB 的边缘实例收集、处理和写入数据。

按照前面方法的步骤，在边缘对原始数据进行缩减采样，但现在我们也将缩减采样的数据写入边缘的 InfluxDB 实例。最后，保存的缩减采样数据被推送到 InfluxDB 的云实例。

1.  在边缘上运行的 InfluxDB 实例中创建一个 bucket。将该存储区称为“设备”，并为该数据设置一小时的保留策略。
2.  在 InfluxDB 的边缘创建另一个 bucket，并将其称为“northbound ”,保留策略为一天。
3.  在 InfluxDB 的云实例中创建一个 bucket。我们将这个存储桶称为“edge_aggregate ”,并将其设置为 30 天保留策略。
4.  在 InfluxDB 的 edge 实例中创建一个任务，该任务对 edge 的“devices”桶中的原始数据进行缩减采样，并每隔一分钟将缩减采样的数据写入 edge 的“northbound”桶中。
5.  在边缘上创建另一个任务，每五分钟将数据从“北向”推到云中的“edge_aggregate”。
6.  将“edge_host”标记注入到传入的数据中。

### 优势

*   快速且易于设置。
*   显著减少发送到云实例的不干净的原始数据量。
*   降低边缘数据连接吞吐量需求。
*   对云和边缘之间的连接中断具有弹性。

### 不足之处

*   需要更多的边缘计算能力。
*   需要更多的边缘内存。
*   需要边缘存储容量。

正如我们所指出的，这些方法各有优缺点，因此请选择最适合您的技术堆栈和使用情形的方法。

您可以跨分布式边缘设备复制或调整这些任务，以最大化您的可用资源。

无论您选择哪种方法，这种类型的解决方案都可以让您更好地观察边缘设备。它还有助于通过减少中央存储实例中数据集的大小来简化整个生态系统中的数据处理。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>