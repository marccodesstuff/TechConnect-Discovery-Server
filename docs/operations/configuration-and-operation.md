# Configuration and Operation

The Discovery Server is pre-configured to run as a standalone service registry for development and testing.

## Port Configuration

The server runs on port **8761**, which is the standard default for Eureka.

```yaml
server:
  port: 8761
```

## Eureka Server Settings

The configuration in `src/main/resources/application.yml` is optimized for a single-node setup:

- `register-with-eureka: false`: The server doesn't try to register with itself as a client.
- `fetch-registry: false`: The server doesn't try to fetch the registry from a peer.
- `wait-time-in-ms-when-sync-empty: 0`: Ensures fast startup in local dev environments.

## The Eureka Dashboard

Once the server is running, you can access the visual dashboard at:

**[http://localhost:8761](http://localhost:8761)**

The dashboard displays:
- **System Status**: General health and environment info.
- **Instances currently registered**: A table of all services that have successfully connected to the registry.
- **General Info**: Memory and CPU usage.

## Database Dependency (Optional)

The `pom.xml` and `application.yml` include references to PostgreSQL. This is **not required** for Eureka's core functionality (which stores the registry in memory). It is included to maintain configuration parity with other microservices in the TechConnect project that may use shared environment variables.

```yaml
spring:
  datasource:
    url: ${SPRING_DATASOURCE_URL:jdbc:postgresql://db:5432/techconnect}
```

If the database is not available, the server will still function as a discovery server, though you may see warnings in the console.
