FROM registry.access.redhat.com/ubi8/ubi:latest

RUN yum -y install java-1.8.0-openjdk-headless openssl && yum -y clean all

# Set JAVA_HOME env var
ENV JAVA_HOME /usr/lib/jvm/java

ARG version=latest
ENV VERSION ${version}

COPY ./scripts/ /bin
COPY ./src/main/resources/log4j2.properties /bin/log4j2.properties

ADD target/hello-world-producer-1.0-SNAPSHOT.jar /

CMD ["/bin/run.sh", "/hello-world-producer-1.0-SNAPSHOT.jar"]