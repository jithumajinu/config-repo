------------jithu majinu--------------

1. First, ensure you have the Maven wrapper in your project. If not, generate it using:
mvn wrapper:wrapper

2. Basic Maven wrapper commands:
# Run the application
./mvnw spring-boot:run

# Clean and install
./mvnw clean install

# Package the application
./mvnw package

# Run tests
./mvnw test

# Clean the project
./mvnw clean

3. If you get a permission denied error, make the wrapper executable:
chmod +x mvnw

4. Running with specific profiles:
./mvnw spring-boot:run -Dspring-boot.run.profiles=dev

5.Running with custom properties:
./mvnw spring-boot:run -Dspring-boot.run.arguments=--server.port=8085

6.Skip tests:
./mvnw clean install -DskipTests

7.Debug mode:
./mvnw spring-boot:run -Dspring-boot.run.jvmArguments="-Xdebug -Xrunjdwp:transport=dt_socket,server=y,suspend=n,address=5005"




-----------------------

# config-server-spring-boot
Central Configuration Server with Spring boot Cloud

#

#config-server

#

## Build Instruction
```
mvn clean install
java -jar .\target\config-server-0.0.1-SNAPSHOT.jar
```

*App runs on port **8888***

##




@EnableConfigServer:
Add the @EnableConfigServer annotation before the Spring Application and build the project. With this annotation, this artifact will act like a spring config server.



application.yml:




@RefreshScope annotation:
By default, the configuration values are read on the client’s startup, and not again. We can force a bean to refresh its configuration — to pull updated values from the Config Server — by annotating with @RefreshScope.
