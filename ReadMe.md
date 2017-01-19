# Camel Spring QuickStart

This quickstart runs a Java application using Spring with Apache Camel.

This example is implemented using solely a Spring XML file (there is no custom Java code).
The source code is provided in the following XML file `src/main/resources/META-INF/spring/camel-context.xml`,
which can be viewed from [github](https://github.com/fabric8io/ipaas-quickstarts/blob/master/quickstart/java/camel-spring/src/main/resources/META-INF/spring/camel-context.xml).

This example uses a timer to trigger a message every 5th second that is routed using a content based router, based on
the message is regarded as high priority or not.


### Building

Navigate to the `camel-spring` folder and the example can be built with

    mvn clean install

### Running the example locally

The example can be run locally using the following Maven goal:

    mvn exec:java


### Running the example in Kubernetes or OpenShift

It is assumed a running Kubernetes platform is already running. If not you can find details how to [get started](http://fabric8.io/guide/getStarted/index.html).

    mvn fabric8:run
    
To list all the running pods in Kubernetes type:

    kubetl get pods

Or on OpenShift type:

    oc get pods

Then find the name of the pod that runs this quickstart, and output the logs from the running pods with:

    kubectl logs <name of pod>

You can also use the fabric8 [web console](http://fabric8.io/guide/console.html) to manage the running pods, and view logs and much more.


#### Integration Testing

The example includes a [fabric8 arquillian](https://github.com/fabric8io/fabric8/tree/master/components/fabric8-arquillian) Kubernetes Integration Test. 
Once the container image has been built and deployed in Kubernetes, the integration test can be run with:

	mvn test -Dtest=*KT

The test is disabled by default and has to be enabled using `-Dtest`. [Integration Testing](https://fabric8.io/guide/testing.html) and [Fabric8 Arquillian Extension](https://fabric8.io/guide/arquillian.html) provide more information on writing full fledged black box integration tests for Kubernetes. 

### More details

You can find more details about running this [quickstart](http://fabric8.io/guide/quickstarts/running.html) on the website.

