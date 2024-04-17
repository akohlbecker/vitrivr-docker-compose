FROM eclipse-temurin:17-jdk

ARG VERSION=v3.12.4 # v3.7.2

#ARG JAVA_OPTS=""
ENV JAVA_OPTS=""

#ARG COMMAND=""
ENV COMMAND=""

RUN apt-get update; apt-get install curl; curl -L -o /cineast-api.jar  https://github.com/vitrivr/cineast/releases/download/$VERSION/cineast-api.jar

ENTRYPOINT exec java $JAVA_OPTS -jar /cineast-api.jar /config.json $COMMAND
