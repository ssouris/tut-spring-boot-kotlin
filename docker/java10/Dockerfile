FROM openjdk:10-jdk

MAINTAINER blogger

USER root
RUN groupadd -r blogger && useradd -r -g blogger blogger
RUN mkdir -p /var/log/eyebrow && chown -R blogger:blogger /var/log/eyebrow
RUN mkdir -p /blogger/ && chown blogger:blogger /blogger

COPY *.jar /blogger/demo.jar
COPY start.sh /blogger/start.sh
RUN chown blogger:blogger /blogger/*.jar && chmod u+x /blogger/start.sh

ENV SERVER_PORT 8080

EXPOSE 8080
ENTRYPOINT ["/blogger/start.sh"]
