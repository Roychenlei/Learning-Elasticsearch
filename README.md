# Learning-Elasticsearch

###一、 Basic Concept
Elasticsearch 是基于Lucene 的搜索引擎。Lucene 是一个强大的开源搜索库。它俩关系就像是汽车 跟引擎的关系。Elasticsearch 是一个实时的分布式搜索分析引擎，被用作全文检索、结构化搜索、分析以及这三个功能的组合。官方定义：
>Elasticsearch is a distributed, RESTful search and analytics engine capable of solving a growing number of use cases. As the heart of the Elastic Stack, it centrally stores your data so you can discover the expected and uncover the unexpected.

### 二、Install Elasticsearch on MacOS
* 安装java ，[oracle](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)官网安装，确认安装成功。
```
  $ java --version  
```
* brew 安装Elasticsearch
```
$ brew update
$ brew install elasticsearch 
$ brew info elasticsearch
```
![](http://upload-images.jianshu.io/upload_images/807985-e61ec9c9eaf2eac2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 三、Try it out
```
$ elasticsearch
```
![chrome plugin: json viewer](http://upload-images.jianshu.io/upload_images/807985-a064e478d98200b4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
一个 Elasticsearch 请求和任何 HTTP 请求一样由若干相同的部件组成：
```
$curl -X<VERB> '<PROTOCOL>://<HOST>:<PORT>/<PATH>?<QUERY_STRING>' -d '<BODY>'
```
Elasticsearch HTTP 服务的端口号，默认是 9200.
PATH是API 的终端路径（例如 _count 将返回集群中文档数量）。
QUERY_STRING 是任意可选的查询字符串参数
BODY是一个 JSON 格式的请求体 (如果请求需要的话)
###四、CRUD
新增记录
```
$curl -X POST 'localhost:9200/accounts/post' -d'{ "title":"elasticsearch","content":"hello, elasticsearch2","tag":"elasticsarch2"}'
```

![](http://upload-images.jianshu.io/upload_images/807985-d5edef1fb23c4245.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
修改记录
```
$curl -X PUT 'localhost:9200/accounts/post/1' -d'{ "title":"elasticsearch","content":"update, elasticsearch","tag":"updated"}'
```

![](http://upload-images.jianshu.io/upload_images/807985-ff3b1043a305c2a8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

删除记录
```
$curl -X DELETE '127.0.0.1:9200/accounts/post/1'
```
![](http://upload-images.jianshu.io/upload_images/807985-9ca11a7a67915bc5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###五、参考链接
[ElasticSearch 官方网站]
(https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started.html）
