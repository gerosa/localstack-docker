# LocalStack Docker
Docker container with [LocalStack](https://github.com/localstack/localstack) and [awslocal](https://github.com/localstack/awscli-local) (a thin wrapper around the AWS command line interface for use with LocalStack).

__To start LocalStack, run:__

```
docker run -d \
   -p 4567-4582:4567-4582 -p 8080:8080 \
   -v /tmp/localstack:/tmp/localstack \
   -v /var/run/docker.sock:/var/run/docker.sock \
   --name localstack \
   gerosa/localstack
```

Optionally you can send a [list of services](http://docs.aws.amazon.com/cli/latest/reference/#available-services) you want to start with the parameter `-e SERVICES=s3,sns,sqs`. Please check the list of services made available by LocalStack.

For more configurations, check the [localstack documentation](https://github.com/localstack/localstack#configurations)

__To call LocalStack, run:__

`docker exec localstack awslocal <service> help`

`docker exec localstack awslocal <service> <command>`


