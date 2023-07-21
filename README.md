# LocalStack DockerCon Demonstration Materials

Repository with code samples for the long-form presentation at DockerCon 2023.

## Prerequisites

-   Docker
-   Python & `pip`
-   Node.js & `npm`
-   LocalStack Pro API key ([free trial key here](https://app.localstack.cloud/))

## Installation & Getting Started

LocalStack can be started in [different ways](https://docs.localstack.cloud/getting-started/installation/). For this presentation, you can start LocalStack with the [LocalStack Docker Extension](https://docs.localstack.cloud/user-guide/tools/localstack-docker-extension/) or through our [Docker Compose](https://docs.localstack.cloud/getting-started/installation/#starting-localstack-with-docker-compose) setup.

Once LocalStack is running in the Docker container, we can issue CLI commands to create and interact with AWS resources. Let's say, for instance, that we want to create a S3 bucket. If you have the [AWS Command Line Interface](https://aws.amazon.com/cli/) installed on your machine, you can simply type:

```bash
aws --endpoint=http://localhost.localstack.cloud:4566 s3 mb s3://demo-bucket
```

To make things simpler, you might want to install  [`awslocal`](https://github.com/localstack/awscli-local), i.e., our wrapper around the AWS CLI. This way, you don't need to set up the endpoint for every CLI command. The previous command would just be:

```bash
awslocal s3 mb s3://demo-bucket

```

You can create and browse resources in LocalStack also from the research browser. Simply, go to our  [Web App](https://app.localstack.cloud/), log in, and click on  _Resources_  in the top navigation bar. You will gain access to our research browser, where each service has a console to manage its resources.

## Sample 1: Deploying a S3 Static Website 

Every programming language tutorial starts with printing a _Hello World_. Let us have the [equivalent](./01-hello-world/) in LocalStack. Host a static website using a Simple Storage Service (S3) bucket to serve static content by provisioning the infrastructure using Terraform in LocalStack. You will configure S3 buckets locally for testing and integration, and make use of LocalStack’s S3 API & `tflocal` CLI to provision infrastructure locally, everything running in the LocalStack Docker container.

## Sample 2: Infrastructure-as-Code Tools and Containerized Applications

We mostly interacted with LocalStack through the AWS CLI so far. However, large systems are hardly built this way. Luckily, LocalStack supports a [wide range of integrations](https://docs.localstack.cloud/user-guide/integrations/) that will cover your favorite Infrastructure-as-Code (IaC) tool. In the following [sample](./02-serverless-api-ecs-apigateway/), we will deploy a containerized application (using Docker, ECS, Cognito, etc) with either Terraform or CloudFormation.

## Sample 3: Cloud Pods

With LocalStack Cloud Pods, you can create persistent state snapshots to enable next-generation state management and team collaboration features for your local development environment. In the following [sample](./03-cloud-pods/), we will create a Cloud Pod and use it to share the state of our LocalStack resources with other developers. We will also learn how to store Cloud Pods on a Docker Hub backend using the ORAS (OCI Registry as Storage) mechanism.
