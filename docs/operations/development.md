# Development Guide

Instructions for building and running the TechConnect Discovery Server.

## Prerequisites

- **Java 17** (JDK)
- **Maven 3.8+**
- (Optional) **Docker**

## Building the Project

The project uses Maven. To package the application into a JAR:

```bash
mvn clean package
```

The resulting JAR will be in `target/discovery-server-0.0.1-SNAPSHOT.jar`.

## Running the Server

### 1. Locally via Maven
```bash
mvn spring-boot:run
```

### 2. via Docker
```bash
docker build -t discovery-server .
docker run -p 8761:8761 discovery-server
```

## Monitoring Health

Spring Boot Actuator is enabled. You can check the server's health status at:

**http://localhost:8761/actuator/health**

## Testing

You can verify the server is working by checking the logs for:
`Eureka started` and `Setting the server's state to UP`.

Once running, try to start another service (like the Opportunity Service) and verify that it appears on the dashboard at `http://localhost:8761`.
