# Hello World in LocalStack

This simple serverless app is the Hello World of LocalStack.
It will deploy an S3 static website with a simple _"Hello World"_ message.

For more information, visit our [docs](https://docs.localstack.cloud/tutorials/s3-static-website-terraform/).

## How to run

Simply start LocalStack with `localstack start -d` and then run the `deploy.sh` script.

Once deployed, you can open the page in the browser: http://testwebsite.s3-website.localhost.localstack.cloud:4566
