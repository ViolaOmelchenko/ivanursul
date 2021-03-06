---
layout: "post"
title:  "Gatling integration tool - making more flexibility"
date: 2015-02-08 08:21:24
permalink: gatling-flexibility
---


I recently had a chance to investigate how to increase flexibility of my integration test, written on gatling and scala.

I have already written around 50 test cases, and I need couple of improvements:

* Be able to change url of my web service. By default, it should run on localhost, but as soon as I will configure continuous delivery, I will need to change web service url to some remote ip. For that needs I am planning to use maven preferences.

* More precise configuration of my setup function. By this time, I had no assertion strategies and I was confused that my tests go green even if some test case failed.
 

## Dynamic web service url

I was hoping that gatling has something like Spring has - placeholders, but it occurs that the only way I can get property from maven is by system property

> val host = System.getProperty("integration.host")

<script src="https://gist.github.com/johnyUA/42c0c8e8963a4443489b.js"></script>

You also need to add additional configuration on your gatling plugin in maven

> &lt;jvmArgs> 
&lt;jvmArg>-Dintegration.host=${integration.url}&lt;/jvmArg>
&lt;/jvmArgs>
 
Where ${integration.url} is taken from maven module properties

Here is full pom.xml

<script src="https://gist.github.com/johnyUA/d9d51e59a8b2119079ee.js"></script>

After this modification, You will be able to change your basicUrl

> mvn test -Dintegration.url=http:${REMOTE_IP}:8080/....

and my test scenarios will run on dedicated server.

Such improvement is very important in case if you are using continuous delivery in your daily development.Here is  an example:

You can configure continuous integration process on your project with two jobs:

One job will run tests, plugins, builds wars, statistics, etc + use tomcat deploy plugin to deploy your war somewhere.
Second job will triggers only if first job will run succesfully. In case of success, second job will run integration tests. And here is the bottleneck, where you will need dynamic web service url. You will configure second job with specific maven instructions for your **REMOTE_IP** - where deployed application from first job will be running.
Global setup configuration

I didn't pay attention to this part of gatling functionality. It occurs for me, that we can configure gatling in the way we want. That's mean that I am free to setup my build in the way of I want, I can configure gatling to fail build only if some percent of requests are failed:

> global.successfulRequests.percent.greaterThan(95)

Note, that by default, every build will be failed only if some compilation errors will occur. In all other cases build will be succesful.

Here is an example of gatling setup

> setUp(...)
.assertions( global.responseTime.mean.lessThan(50), 
global.responseTime.max.between(50, 500),     
global.successfulRequests.count.greaterThan(1500),
global.allRequests.percent.is(100)

Here is full scala object

<script src="https://gist.github.com/johnyUA/6417fbc05aa99fa8d89f.js"></script>

That's it for today, I hope, in near future I will publish something about integration between jenkins and gatling(gatling has plugin for jenkins :)).