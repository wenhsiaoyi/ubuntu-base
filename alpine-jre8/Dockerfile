# Base Alpine Linux based image with OpenJDK JRE only
FROM openjdk:8-jre-alpine3.9

ENV LANG en_US.UTF-8
RUN locale-gen $LANG

# copy application WAR (with libraries inside)
#COPY target/spring-boot-*.war /app.war
# specify default command
#CMD ["/usr/bin/java", "-jar", "-Dspring.profiles.active=test", "/app.war"]

CMD ["bash"]
