
FROM docker.io/java:openjdk-8-jre

MAINTAINER Hygieia@capitalone.com

RUN mkdir /hygieia /hygieia/config

COPY *.jar /hygieia/
COPY jenkins-codequality-properties-builder.sh /hygieia/

WORKDIR /hygieia

VOLUME ["/hygieia/logs"]

CMD ./jenkins-build-properties-builder.sh && \
  java -jar jenkins-codequality.jar --spring.config.location=/hygieia/config/hygieia-jenkins-codequality-collector.properties

