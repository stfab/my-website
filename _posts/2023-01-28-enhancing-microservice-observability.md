---
layout: post
title: "Observability of Microservices With Datadog"
description: "This article delves into the topic of observability when deploying microservices to Kubernetes with the SaaS Datadog as an example."
author: "Fabian Stadler"
categories: tech
tags: [microservices,tools]
image: assets/img/cateyes.png
image_description: "An image of a cat with blue eyes as a metaphor for observability."
permalink: 2023/01/enhancing-microservice-observability.html
lang: en
---

In today's fast-paced and ever-changing software development landscape, deploying microservices to Kubernetes has become a popular and effective way to build and manage large, complex systems. However, as the number of microservices in a system increases, so does the complexity of monitoring and understanding the behavior and performance of those services in production. This is where observability comes in. In this article, we'll explore why observability is crucial when deploying microservices to Kubernetes, and what you need to know to effectively monitor and troubleshoot your microservices in a Kubernetes environment. For this, we will take the monitoring SaaS Datadog as an example.

## What is Datadog?

Datadog is a cloud-based monitoring and analytics platform that provides detailed insight into the performance and health of IT infrastructure, applications, and log data. It allows you to collect, analyze, and visualize metrics and traces from various sources, such as servers, containers, and cloud services. The platform includes a variety of features, such as real-time monitoring, alerting, anomaly detection, and dashboards, that help organizations to identify and troubleshoot issues with their systems, as well as optimize performance and availability. Additionally, Datadog provides a powerful query language that allows you to create custom metrics and alerts. It support multi-cloud, hybrid, and on-premises environments.

## Enhance the observability of microservices with Datadog

Datadog can help to enhance the observability of microservices by providing a comprehensive view of the performance and health of the microservices and their underlying infrastructure. With features such as metrics collection, tracing, log aggregation, dashboards and alerts, and Kubernetes integration, Datadog can give you the visibility you need to monitor and troubleshoot issues with your microservices.

By collecting and aggregating metrics, traces, and logs from the microservices and their dependencies, such as databases and message queues, Datadog can provide real-time insights into the performance and resource usage of your microservices, enabling you to detect and resolve issues quickly.

Additionally, with the Kubernetes integration, Datadog can collect Kubernetes-specific metrics, such as resource usage and performance of the nodes and pods, which helps to identify issues with the microservices and the Kubernetes infrastructure they are running on.

![Query Traces & Logs in Datadog](/assets/img/datadog-logexplorer.png "Query Traces & Logs in Datadog"){:style="float: center"}
*Query Traces & Logs With The Log Explorer, Image source: Datadog*

## Advantages of using Datadog over other log services

Datadog provides a comprehensive and flexible monitoring solution that can help organizations to gain a deeper understanding of their systems and improve the overall availability and performance of their microservices. For example, it offers:

  * Comprehensive monitoring: Datadog provides a comprehensive monitoring solution that includes metrics collection, tracing, and log aggregation, which allows you to gain a complete view of the performance and health of your systems, rather than just logs.
  * Real-time monitoring: Datadog allows you to monitor your systems in real-time, which can help you detect and troubleshoot issues as they occur, rather than after the fact.
  * Anomaly detection: Datadog includes a built-in anomaly detection feature that can automatically identify abnormal behavior in your metrics and alert you to potential issues.
  * Customizable dashboards: Datadog provides a variety of visualization options, such as dashboards, which can be customized to meet the specific needs of your organization.
  * Multi-cloud and hybrid support: Datadog supports multi-cloud and hybrid environments and can monitor resources across different cloud providers, on-premises and edge.
  * Integrations: Datadog has a large number of integrations with other tools and services, such as AWS, GCP, Azure, Slack, PagerDuty, etc., which allows you to easily integrate Datadog with your existing workflow and tools.

## Send logs of a .NET service to Datadog

Sending logs from a .NET service to Datadog is an essential step in monitoring and troubleshooting your application. There are several ways to achieve this, each with its own set of advantages and disadvantages.

The first option is to use the Datadog Agent. This is a lightweight software that can be installed on your servers to collect and forward logs to the Datadog platform. You can configure the Agent to collect logs from your .NET service by specifying the file path of the log files in the Agent's configuration file.

Another option is to use the Datadog .NET Logs Library. This library allows you to send logs directly from your .NET service to the Datadog platform. You can install the library using NuGet and then use the provided APIs to send logs to Datadog.

A third option is to use a log shipper, such as Filebeat. With this approach, you will need to configure Filebeat to collect the logs from your .NET service and forward them to the Datadog platform using the Datadog output plugin.

Finally, if you are using a cloud provider such as AWS, Azure, or GCP, you may use their service to forward your logs to Datadog.

Regardless of the method you choose, you will also need to configure the Datadog platform to receive and process the logs. This can be done by creating a log pipeline in the Datadog platform and specifying the source and format of the logs.

It is important to note that before sending the logs to Datadog, it is crucial to make sure that the logs are in a structured format and contain the necessary information to troubleshoot and diagnose issues.

## Export traces and logs of a .NET service with OpenTelemetry and Serilog

You can instrument and send telemetry data from your .NET application to Datadog using OpenTelemetry and Serilog. Install the OpenTelemetry package and the Datadog exporter using NuGet by running the following command:

```bash
dotnet add package OpenTelemetry
dotnet add package OpenTelemetry.Exporter.Datadog
```

In your application, configure the OpenTelemetry exporter to send telemetry data to Datadog. You will need to specify your Datadog API key and provide a service name for your application. You can do this in the Startup.cs file or in any other configuration file in your application.


```csharp
using OpenTelemetry;
using OpenTelemetry.Exporter.Datadog;
var exporter = new DatadogExporter(new DatadogExporterOptions()
{
    ApiKey = "YOUR_API_KEY",
    ServiceName = "your-service-name"
});

TelemetryConfiguration configuration = TelemetryConfiguration.CreateDefault();
configuration.AddExporter(exporter);
```

Use the OpenTelemetry APIs to instrument your code and send telemetry data to Datadog. The OpenTelemetry package provides several APIs for creating spans, metrics, and traces that can be used to instrument your code.

You can also use the Serilog package to log structured data. It can be integrated to your application by installing the package and configuring it to write to the console, a file or a specific sink such as Datadog. You can use the Serilog.Sinks.Datadog package to send log data to Datadog. In the Datadog platform, you will need to configure a log pipeline to receive and process the logs sent by Serilog.

By using OpenTelemetry and Serilog together, you can gain a comprehensive understanding of your application's performance and behavior, including detailed traces and metrics, as well as structured log data. This can help you to quickly identify and troubleshoot

## Detect unoptimized code and performance bottlenecks

Datadog offers a range of features that can assist in detecting unoptimized code and performance bottlenecks in your applications. The Code Profiling feature in Datadog APM allows for profiling of your application's performance, identifying which parts of your code are taking the most time to execute and pinpointing unoptimized areas that may be causing bottlenecks.

Tracing requests as they flow through your application with Datadog APM can also help identify bottlenecks and latency issues in your application's architecture. Anomaly Detection automatically identifies abnormal behavior in metrics and alerts you to potential issues.

Customizable dashboards and visualization options, such as those provided by Datadog, can assist in understanding the performance of your applications and identifying areas requiring optimization.

## Generate reports for dev teams and stakeholders

![Create Dashboard Reports in Datadog](/assets/img/datadog-dashboard.png "Create Dashboard Reports in Datadog"){:style="float: center"}
*Create Dashboard Reports, Image source: Datadog*

Finally, Datadog offers a variety of features to help generate performance and security reports. With custom dashboards, you can visualize metrics, traces, and logs to create performance reports that display key information such as response time, error rate, and throughput. 

The Reports feature allows for easy generation and scheduling of custom reports in various formats, including PDF, CSV, and JSON. These reports can be customized to include data most relevant to your organization and can include metrics, traces, and logs. 

Additionally, the Datadog Monitor service enables the creation of monitors that trigger alerts when specific conditions are met. These monitors can be used to generate security reports that provide information on security-related metrics, such as the number of failed login attempts or blocked IPs.

## Conclusion

Datadog is a powerful monitoring and observability platform that offers a wide range of features for monitoring and troubleshooting applications, networks and infrastructure. Some of the advantages of using Datadog include its ability to collect and aggregate metrics, traces, and logs from a wide variety of sources, its support for custom dashboards and alerting, and its ability to automatically detect and alert on anomalies. It also provides a wide variety of integrations with other tools, such as cloud providers, security tools, and databases.

However, Datadog may have some disadvantages as well, such as its high cost for some large enterprise use cases and its relatively steep learning curve for new users. Additionally, it may not be the best fit for organizations with strict security and regulatory requirements. As always, it depends on the business requirements if working with a SaaS like Datadog is optimal.
