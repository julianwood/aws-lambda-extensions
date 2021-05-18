# AWS Lambda Extensions
[![AWS Lambda extensions](/img/LambdaExtensions.png)](https://aws.amazon.com/blogs/compute/introducing-aws-lambda-extensions-in-preview/)

AWS Lambda Extensions are a new way for tools to more easily integrate deeply into the Lambda execution environment to control and participate in Lambda’s lifecycle. 

You can use extensions to integrate your Lambda functions with your preferred monitoring, observability, security, and governance tools. You can choose from a broad set of tools provided by AWS Lambda partners or you can create your own Lambda extensions.

Extensions use the Extensions API, a new HTTP interface, to register for lifecycle events and get greater control during function initialization, invocation, and shutdown. They can also use environment variables to add options and tools to the runtime, or use wrapper scripts to customize the runtime startup behavior.

For more information, see [Using AWS Lambda extensions](https://docs.aws.amazon.com/lambda/latest/dg/using-extensions.html).

> **Note**: an internal extension runs in the runtime process, and shares the same lifecycle as the runtime. An external extension runs as a separate process in the execution environment. The extension runs in parallel with the function's runtime. It is initialized before the function is invoked and continues to run after the function invocation is complete

## Sample demos and examples

In this repository you'll find a number of different sample projects from AWS and partners to help you get started with building your own extension.

## AWS examples

### Demo examples

[Demo: AWS AppConfig](awsappconfig-extension-demo/) | [Demo: Custom runtime extension](custom-runtime-extension-demo/) | [Demo: Cache Extension](cache-extension-demo/)
:----  | :----  | :----
A demo showing [AWS Lambda](https://aws.amazon.com/lambda/) using an extension using [AWS AppConfig](https://docs.aws.amazon.com/appconfig/latest/userguide/what-is-appconfig.html) as explained in the blog post [Introducing Lambda Extensions](https://aws.amazon.com/blogs/compute/introducing-aws-lambda-extensions-in-preview/). | A demo showing how to learn about the Extensions API as explained in the blog post [Building Extensions for AWS Lambda](https://aws.amazon.com/blogs/compute/building-extensions-for-aws-lambda-in-preview/). | The cache demo code sample is written in Go and acts as a companion process which a Lambda function can use to both data cache (using DynamoDB) and configuration cache (using Systems Manager Parameter Store).
| [View repo](awsappconfig-extension-demo/) | [View repo](custom-runtime-extension-demo/) | [View repo](cache-extension-demo/) 

### Sample extension examples by language

[Extension in Go](go-example-extension/) |  [Extension in Python](python-example-extension/) |[Extension in Node.js](nodejs-example-extension/)
:----  | :----  | :----
Sample: how to get a basic extension written in Go up and running. | Sample: how to get a basic extension written in Python 3 up and running. | Sample: how to get a basic extension written in Node.js 12 up and running.
| [View repo](go-example-extension/) | [View repo](python-example-extension/) | [View repo](nodejs-example-extension/) 

[Extension in Java 11](java-example-extension/) | [Extension in C#.NET](csharp-example-extension/)
:----  | :---- 
Sample: how to get a basic extension written in Java 11 up and running. | Sample: how to get a basic extension written in Python 3 up and running. | Sample: how to get a basic extension written in C# up and running.
| [View repo](java-example-extension/) | [View repo](csharp-example-extension/)

### Logs API demo and sample extension examples

[Logs API extension in Go](go-example-logs-api-extension/) |  [Logs API extension in Python](python-example-logs-api-extension/) | [Logs API extension in Python for Elasticsearch](python-example-elasticsearch-extension/)
:----  | :----  | :----
The provided code sample demonstrates how to get a basic Logs API extension written in Go up and running. | The provided code sample demonstrates how to get a basic Logs API extension written in Python 3 up and running. | The provided code sample demonstrates how to get a basic Logs API extension for Elasticsearch written in Python 3 up and running.
| [View repo](go-example-logs-api-extension/) | [View repo](python-example-logs-api-extension/) | [View repo](python-example-elasticsearch-extension/)

[Logs API extension in Node.js](nodejs-example-logs-api-extension/) |  [Demo: Logs to Amazon S3 extension: zip archive](s3-logs-extension-demo-zip-archive/) | [Demo: Logs to Amazon S3 extension: container image ](s3-logs-extension-demo-container-image/)
:----  | :----  | :----
Sample: how to get a basic Logs API extension written in Node.js 12 up and running. | Demo to send logs directly from Lambda to S3, see the blog post [Using AWS Lambda extensions to send logs to custom destinations](https://aws.amazon.com/blogs/compute/using-aws-lambda-extensions-to-send-logs-to-custom-destinations/) | Demo to send logs directly from Lambda to S3, This example packages the extension and function as separate container images. | [View repo](s3-logs-extension-demo-zip-archive/) | [View repo](s3-logs-extension-demo-container-image/)

### Other extension examples

[Adaptive Batching extension in Go](go-example-adaptive-batching-extension/) | [Inter-process communication extension in Go](go-example-ipc-extension/) | [Crash uploader extension in Go](go-example-crash-uploader-extension/)
:----  | :---- | :----
How to use the Logs API extension written in Go to adaptively batch log data to a destination (S3). | A sample extension written in Go that acts as a companion process which the AWS Lambda function runtime can communicate with. | A sample extension that looks for core dumps in the execution environment and uploads them to an Amazon S3 bucket for later inspection and troubleshooting.
[View repo](go-example-adaptive-batching-extension/) | [View repo](go-example-ipc-extension/) | [View repo](go-example-crash-uploader-extension/)

### Wrapper script extension examples by language
[Wrapper script in Bash](bash-example-wrapper/) | [Wrapper script in Python](python-example-wrapper/) | [Wrapper script in Ruby](ruby-example-wrapper/)
:----  | :----  | :----
How to to get a wrapper script written in Bash up and running. | How to to get a wrapper script written in Python up and running. | How to to get a wrapper script written in Ruby up and running.
[View repo](bash-example-wrapper/) | [View repo](python-example-wrapper/) | [View repo](ruby-example-wrapper/)

## AWS Lambda Ready Partner open-source examples

[![Coralogix](/img/Coralogix-Logo.png)](https://coralogix.com/integrations/coralogix-extensions-for-aws-lambda/) | [![HashiCorp Vault](/img/HashiCorpVault-Logo.png)](https://www.hashicorp.com/blog/aws-lambda-extensions-for-hashicorp-vault/) | [![Honeycomb](/img/Honeycomb-Logo.png)](https://www.honeycomb.io/blog/announcing-honeycombs-extension-for-the-aws-lambda-runtime-logs-api/)
:----  | :----  | :----
Coralogix is a machine data analytics SaaS platform that drastically improves the delivery & maintenance process for software providers. The extension provides full integration of Lambda functions with the Coraligix service | The HasiCorp Vault extension makes it easy for operators to manage secrets and make them available for developers to use within their function code, without having to make their functions Vault aware. | The Honeycomb Lambda extension allows you to send messages from your Lambda function to Honeycomb by just writing JSON to stdout. The extension receives the messages and forwards them to Honeycomb as an event.
[View extension](https://github.com/coralogix/aws-lambda-extension) | [View extension](https://github.com/hashicorp/vault-lambda-extension) | [View extension](https://github.com/honeycombio/honeycomb-lambda-extension)

[![Lumigo](/img/Lumigo-Logo.jpg)](https://docs.lumigo.io/docs/lambda-extensions) | [![New Relic](/img/NewRelic-Logo.png)](https://newrelic.com/blog/nerdlog/aws-lambda-extensions-integrations) | [![Sumo Logic](/img/SumoLogic-Logo.png)](https://www.sumologic.com/blog/lambda-extensions/)
:----  | :----  | :----
Lumigo helps identify functions that are CPU- or network-bound. This allows you to improve their performance by increasing their memory size. | An AWS Lambda extension to collect, enhance, and transport telemetry data from your AWS Lambda functions to New Relic. This lightweight AWS Lambda Extension runs alongside your AWS Lambda functions and automatically handles the collection and transport of telemetry data from supported New Relic serverless agents. | The Sumo Logic extension, along with Sumo Logic's continuous intelligence platform, enables you to get instance visibility into the health and performance of your mission-critical serverless applications.
[View extension](https://github.com/lumigo-io/lambda-log-shipper) | [View extension](https://github.com/newrelic/newrelic-lambda-extension) | [View extension](https://github.com/SumoLogic/sumologic-lambda-extensions)

## Available AWS Lambda Ready Partner extensions
* [AppDynamics](https://docs.appdynamics.com/display/PRO20X/Use+the+AppDynamics+AWS+Lambda+Extension+to+Instrument+Serverless+APM+at+Runtime): The AppDynamics AWS Lambda Extension provides automatic instrumentation of Node.js or Python Lambda functions to provide visibility and alerting on function performance in a broader business context
* [Check Point CloudGuard](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk172491&partition=Advanced&product=CloudGuard): Check Point CloudGuard Serverless Protection is a Lambda Layer/Extension-based runtime protection solution providing zero-configuration security for Lambda Functions.
* [Datadog](https://docs.datadoghq.com/serverless/datadog_lambda_library/extension/): The Datadog extension brings comprehensive, real-time visibility to your serverless applications. Combined with Datadog’s existing AWS integration, you get metrics, traces, and logs to help you monitor, detect, and resolve issues at any scale.
* [Dynatrace](https://www.dynatrace.com/support/help/technology-support/cloud-platforms/amazon-web-services/integrations/deploy-oneagent-as-lambda-extension/): The Dynatrace AWS Lambda extension delivers end-to-end visibility into traces and metrics and leverages AI for automated error detection and root cause analysis across the entire application stack.
* [Epsagon](https://docs.epsagon.com/docs/aws-lambda-layer): Epsagon’s extension listens to invocation events, stores traces, and sends them in parallel to Lambda function executions. This helps reduce the overhead of distributed tracing and improve performance.
* [HashiCorp Vault](https://www.hashicorp.com/blog/aws-lambda-extensions-for-hashicorp-vault): The HasiCorp Vault extension makes it easy for operators to manage secrets and make them available for developers to use within their function code, without having to make their functions Vault aware.
* [Lumigo](https://docs.lumigo.io/docs/lambda-extensions): Lumigo helps identify functions that are CPU- or network-bound. This allows you to improve their performance by increasing their memory size.
* [New Relic](https://docs.newrelic.com/docs/serverless-function-monitoring/aws-lambda-monitoring/get-started/monitoring-aws-lambda-serverless-monitoring): An AWS Lambda extension to collect, enhance, and transport telemetry data from your AWS Lambda functions to New Relic. This lightweight AWS Lambda Extension runs alongside your AWS Lambda functions and automatically handles the collection and transport of telemetry data from supported New Relic serverless agents.
* [Sentry](https://docs.sentry.io/product/integrations/aws-lambda/): Sentry’s application monitoring platform helps every developer diagnose, fix, and optimize the performance of their Lambda functions. Over 1M developers already ship better software with Sentry.
* [Sumo Logic](https://www.sumologic.com/blog/lambda-extensions/): The Sumo Logic extension, along with Sumo Logic's continuous intelligence platform, enables you to get instance visibility into the health and performance of your mission-critical serverless applications.
* [Thundra](https://apm.docs.thundra.io/performance/zero-overhead-with-lambda-extensions): Thundra Lambda extension is a companion process that provides asynchronous telemetry data (traces, metrics, logs) reporting functionality to its agents. Thundra's agents add zero network delay.

## Additional Resources
* [Introducing AWS Lambda Extensions](https://aws.amazon.com/blogs/compute/introducing-aws-lambda-extensions-in-preview/)
* [Building Extensions for AWS Lambda](https://aws.amazon.com/blogs/compute/building-extensions-for-aws-lambda-in-preview/)
* [Using AWS Lambda extensions to send logs to custom destinations](https://aws.amazon.com/blogs/compute/using-aws-lambda-extensions-to-send-logs-to-custom-destinations/)
* [Working with Lambda layers and extensions in container images](https://aws.amazon.com/blogs/compute/working-with-lambda-layers-and-extensions-in-container-images/)
* [AWS AppConfig integration with Lambda extensions](https://docs.aws.amazon.com/appconfig/latest/userguide/appconfig-integration-lambda-extensions.html)

## Contributing guidelines
See [CONTRIBUTING](CONTRIBUTING.md) for more information.

## Security issue notifications
If you discover a potential security issue in this project we ask that you notify AWS/Amazon Security via our [vulnerability reporting page](http://aws.amazon.com/security/vulnerability-reporting/). Please do **not** create a public github issue.

## Licensing

This library is licensed under the MIT-0 License. See the [LICENSE](LICENSE) file.

