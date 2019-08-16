# aws-resources-exporter

Prometheus exporter for AWS resources

This was made as a complement to [CloudWatch Exporter](https://github.com/prometheus/cloudwatch_exporter) to get resource information that are useful to keep around as metrics in Prometheus but are out of scope for CloudWatch Exporter.

## Running this software

### From binaries

Download the most suitable binary from [the releases tab](https://github.com/app-sre/aws-resources-exporter/releases)

Then:

    ./aws-resources-exporter <flags>

### Using the container image

    docker run --rm -d -p 9115:9115 \
        --name aws-resources-exporter \
        --env AWS_ACCESS_KEY_ID=AAA \
        --env AWS_SECRET_ACCESS_KEY=AAA \
        --env REGION=AAA \
        quay.io/app-sre/aws-resources-exporter:latest

## Building the software

### Local Build

    make build

### Building docker image

    make image image-push

## Configuration

AWS credentials can be passed as environment variables `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY`. AWS region must be passed via `REGION`.

To view all available command-line flags, run `./aws-resources-exporter -h`.

## License

Apache License 2.0, see [LICENSE](LICENSE).
