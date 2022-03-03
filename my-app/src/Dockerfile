FROM maven:3.5-jdk-8 AS build
        WORKDIR /usr/src/app
        COPY src ./src
        COPY pom.xml .
        RUN mkdir -p /root/.m2 \
    && mkdir /root/.m2/repository
# Copy maven settings, containing repository configu/usr/src/app/target/rations
        COPY settings.xml /root/.m2

        RUN mvn -s /root/.m2/settings.xml clean -Dmaven.test.skip=true package

  FROM java:8-jdk-alpine

  COPY --from=build /usr/src/app/target/*.jar /opt/customerjarapp.jar

CMD  ["java", "-jar", "/opt/customerjarapp.jar"]
