FROM openjdk:8u151-jdk-alpine3.7
  
EXPOSE 8080
 
ENV APP_HOME /usr/src/app

COPY target/secretsanta-0.0.1-SNAPSHOT.jar $APP_HOME/app.jar

WORKDIR $APP_HOME

RUN mkdir -p /usr/local/newrelic

ADD ./newrelic/newrelic.jar /usr/local/newrelic/newrelic.jar

ADD ./newrelic/newrelic.yml /usr/local/newrelic/newrelic.yml
 
ENTRYPOINT ["java","-javaagent:/usr/local/newrelic/newrelic.jar","-jar","/usr/src/app/app.jar"]
