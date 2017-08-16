FROM openjdk:7-jre
MAINTAINER Dean Giberson <dean@deangiberson.com>

# Create working space
WORKDIR /_var/dynamodb_wd

# Default port for DynamoDB Local
EXPOSE 8000

# Get the package from Amazon
RUN wget -O /tmp/dynamodb_local_latest https://s3-us-west-2.amazonaws.com/dynamodb-local/dynamodb_local_latest.tar.gz && \
    tar xfz /tmp/dynamodb_local_latest && \
    rm -f /tmp/dynamodb_local_latest


# Add VOLUMEs to allow backup of config, logs and databases
VOLUME ["/_var/dynamodb_local",]


# Default command for image
ENTRYPOINT ["/usr/bin/java", "-Djava.library.path=.", "-jar", "DynamoDBLocal.jar", "-dbPath", "/_var/dynamodb_local"]
CMD ["-port", "8000"]
