# alibaba-test
阿里一面笔试题
题目：

假设本地有一个文件夹，文件夹下面有若干文件（文件数大于50小于100），文件的存储格式是文本格式（后缀名是.txt)，文件的大小每个文件不会超过100k。

### 文件格式如下：
``

2000102，100，98.3

2000103，101，73.3

2000104，102，98.3

2000105，100，101.3

2000106，101，45.3
......

``
### 文件格式说明：文件每行都由三列构成，第一列是一个id，第二列是分组groupId, 第三列是指标quota。

id的数据类型是String, groupId的数据类型String, quota的数据类型float。

## 功能要求：

### 1.对文件夹下面所有文件的内容进行合并排序，输出按照分组升序排序之后，每个分组下面的最小指标值。比如上面的数据输出结果为：
``

100，2000102，98.3

101，2000106，45.3

102，2000104，98.3

``

## 非功能要求

1.文件读取要有线程池来执行，线程池的大小固定为10，文件内容需要存储到指定的内存数据结构当中。

2.查找要求有独立线程来执行，直接消费读取线程池产生的内存数据结构。

3.文件读取和排序要求并发作业，文件读取只要产生了数据，就可以把数据交给排序线程进行消费，计算最小值。

## 代码结构要求

1.重上面的要求语意里面抽象出合适的设计模式。

2.需要考虑多线程的并发控制，同步机制。

3.代码实现只能用JDK1.6或者1.8自带的工具类
