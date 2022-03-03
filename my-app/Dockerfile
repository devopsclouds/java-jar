FROM  maven:3.8.4-openjdk-11
        WORKDIR /usr/src/app
        COPY src ./src
        COPY pom.xml .
        RUN mkdir -p /root/.m2 \
    && mkdir /root/.m2/repository
# Copy maven settings, containing repository configu/usr/src/app/target/rations
        COPY settings.xml /root/.m2

        RUN mvn -s /root/.m2/settings.xml clean  sonar:sonar
