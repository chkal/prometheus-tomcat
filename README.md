# Prometheus Tomcat

This project builds on top of [Prometheus JVM Client](https://github.com/prometheus/client_java) and
provides collectors for Apache Tomcat.

Currently it supports collectors for:

  * The GlobalRequestProcessor
  * Tomcat's session manager
  

## Installation

Add the following dependency to your `pom.xml`:

```xml
<dependency>
  <groupId>de.chkal.prometheus.tomcat</groupId>
  <artifactId>prometheus-tomcat</artifactId>
  <version>1.0.0</version>
</dependency>
```
    

## Configuration

Please note that you have to first set up the [Prometheus JVM Client](https://github.com/prometheus/client_java)
as described in the corresponding documentation.

Then register the Tomcat collectors just like other collectors.

```java
new TomcatRequestMetricsCollector().register();
new TomcatSessionMetricsCollector().register();
```

If you want to register the collectors to a specific `CollectorRegistry`, just pass it to the `register()` method:

```java
new TomcatRequestMetricsCollector().register(registry);
new TomcatSessionMetricsCollector().register(registry);
```

And that's it. :-)

