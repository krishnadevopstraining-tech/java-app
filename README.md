# Krishna Devops Training

This is a Spring Boot web application that displays "Krishna Devops Training" on the main page with navigation to About and Contact pages.

## Prerequisites

- Java 17 or higher
- Maven 3.6+

## Running the Application

1. Clone or navigate to the project directory.
2. Run the application using Maven:

   ```bash
   mvn spring-boot:run
   ```

3. Open your browser and go to `http://localhost:8080` to see the main page.

## Building the JAR

To build a deployable JAR file:

```bash
mvn clean package
```

The JAR file will be created in the `target/` directory as `krishna-devops-training-0.0.1-SNAPSHOT.jar`.

## Deploying the JAR

To run the JAR file:

```bash
java -jar target/krishna-devops-training-0.0.1-SNAPSHOT.jar
```

The application will start on port 8080 by default.

## Troubleshooting

- Ensure Java and Maven are installed and in your PATH.
- If port 8080 is in use, you can change it in `src/main/resources/application.properties` by adding `server.port=8081` or another port.