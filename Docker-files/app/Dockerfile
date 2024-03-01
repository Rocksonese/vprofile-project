# Stage 1: Build the application
FROM openjdk:11 AS BUILD_IMAGE

LABEL PROJECT="vprofile" \
      Author="Rockson"

RUN apt-get update && apt-get install -y maven git

# Create a working directory
WORKDIR /app

# Clone the repository and build the project
RUN git clone https://github.com/AcruKap/vprofile-project.git \
    && cd vprofile-project \
    && git checkout docker \
    && mvn install

# Stage 2: Create the final image with Tomcat
FROM tomcat:9-jre11

# Remove the default Tomcat webapps
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy the WAR file from the build image to the Tomcat webapps directory
COPY --from=BUILD_IMAGE /app/vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# Expose the Tomcat port
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]
