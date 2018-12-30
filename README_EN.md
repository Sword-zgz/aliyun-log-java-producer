# Aliyun LOG Java Producer

[![Build Status](https://travis-ci.org/aliyun/aliyun-log-producer.svg?branch=master)](https://travis-ci.org/aliyun/aliyun-log-producer-java)
[![License](https://img.shields.io/badge/license-Apache2.0-blue.svg)](/LICENSE)

[中文版 README](/README.md)

The Aliyun LOG Java Producer is an easy-to-use, highly configurable Java library that helps you send data to [Aliyun Log Service](https://www.alibabacloud.com/zh/product/log-service). It designed for Java applications which running in big data and high concurrency scenarios.

## Feature
1. Thread safety - all methods exposed by the producer are thread-safe.
2. Asynchronous - a call to the send method usually returns immediately and does not wait for the data to be sent or a response to be received from the server.
3. Automatic retry - it provides an automatic and configurable retry mechanism for retriable exception.
4. Traceability - the caller can not only obtain the information about whether the current data has been sent successfully, but also the attempts information related to the data through callback or future.
5. Context restore - the logs generated by the same producer are in the same context, and the relevant logs before and after a certain log can be viewed at the server side.
6. Graceful shutdown - when the close method falls back, it ensures that all data cached by producer can be processed and the caller can be notified accordingly.

## Advantages

The following list represents some of the major advantages to using the producer library to send data to log service.

### High performance
The producer library can help build high-performance producer application. To achieve the throughput needed, producers must implement complicated logic, such as batching or multithreading, in addition to retry logic. The producer library performs all of these tasks for you.

### Asynchronous & non-blocking
If the available memory is sufficient, the producer will buffer the data before sending them to log service, it does not force the caller application to block and wait for a confirmation that the data has arrived at the server before continuing execution. The caller can get the result of data transmission through the returned future object or the registerd callback.

### Controllable resources usage
The size of memory used by the producer can be controlled by parameters as well as the number of threads used to perform data sending tasks. This can avoid unrestricted resource consumption by producer on the one hand, and allows you to balance resource consumption and write throughput according to the actual situation on the other.

## Installation

### Maven users
Add this dependency to your project's POM:
```
<dependency>
    <groupId>com.aliyun.openservices</groupId>
    <artifactId>aliyun-log-producer</artifactId>
    <version>0.0.6</version>
</dependency>
<dependency>
    <groupId>com.aliyun.openservices</groupId>
    <artifactId>aliyun-log</artifactId>
    <version>0.6.28</version>
</dependency>
<dependency>
    <groupId>com.google.protobuf</groupId>
    <artifactId>protobuf-java</artifactId>
    <version>2.5.0</version>
</dependency>
```

### Gradle users
```
compile 'com.aliyun.openservices:aliyun-log-producer:0.0.6'
compile 'com.aliyun.openservices:aliyun-log:0.6.28'
compile 'com.google.protobuf:protobuf-java:2.5.0'
```

## Sample application

https://github.com/aliyun/aliyun-log-producer-sample

## Feedback
If you have further questions please open a [GitHub Issue](https://github.com/aliyun/aliyun-log-producer/issues), or [sumbit a ticket](https://workorder.console.aliyun.com/#/ticket/createIndex).