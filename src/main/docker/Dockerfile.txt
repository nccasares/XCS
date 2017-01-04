FROM dockerfile/java:oracle-java8

VOLUME /tmp
ADD artifact.jar /opt/artifact/
EXPOSE 8080
WORKDIR /opt/artifact/
CMD ["java", "-Djava.security.egd=file:/dev/./urandom", "-Xms512m", "-Xmx1g", "-jar", "artifact.jar"]
