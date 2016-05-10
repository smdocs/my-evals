# Initial Notes on JMXtrans

####[JMXTrans Website](http://www.jmxtrans.org/)

1. Installed jmxtrans by downloading the zip file from the website. However the jmxtrans-all.jar file was 
    missing in the zip file. Downloaded the laatest jmxtrans-all.jar file and copied it into the INSTALL directory.
    
2. Modified the example.json file to monitor a local Cassandra database.

Here is the basic config file, I used to monitor Cassandra

```json
{
  "servers" : [ {
    "port" : "7199",
    "host" : "localhost",
    "queries" : [ {
      "outputWriters" : [ {
        "@class" : "com.googlecode.jmxtrans.model.output.StdOutWriter",
        "settings" : {
        }
      } ],
      "obj" : "java.lang:type=Memory",
      "attr" : [ "HeapMemoryUsage", "NonHeapMemoryUsage" ]
    }, {
      "outputWriters" : [ {
        "@class" : "com.googlecode.jmxtrans.model.output.StdOutWriter",
        "settings" : {
        }
      } ],
      "obj" : "java.lang:name=CMS Old Gen,type=MemoryPool",
      "attr" : [ "Usage" ]
    }, {
      "outputWriters" : [ {
        "@class" : "com.googlecode.jmxtrans.model.output.StdOutWriter",
        "settings" : {
        }
      } ],
      "obj" : "java.lang:name=ConcurrentMarkSweep,type=GarbageCollector",
      "attr" : [ "LastGcInfo" ]
    } ],
    "numQueryThreads" : 2
  } ]
}

```

##### Next Steps

- Try collecting the output and save it in ElasticSearch
- Try more complex queries to monitor a large number of JVMs
