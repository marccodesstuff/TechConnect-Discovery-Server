# TechConnect Discovery Server

The service registry for the TechConnect microservices ecosystem. Built with Spring Cloud Netflix Eureka and Java 17.

## 📖 Documentation

A comprehensive guide to the operation, configuration, and architecture of this repository can be found in the **[docs/ folder](./docs/README.md)**.

### Quick Links
- **[System Context](./docs/operations/system-context.md)** – Role as the service registry.
- **[Configuration & Operation](./docs/operations/configuration-and-operation.md)** – Eureka settings and the dashboard.
- **[Development Guide](./docs/operations/development.md)** – Build and run instructions.

## Quick Start (Docker)

The discovery server is essential for the TechConnect ecosystem to function. Run it via Docker:

```bash
docker build -t techconnect-discovery-server .
docker run -p 8761:8761 techconnect-discovery-server
```

Once running, access the Eureka dashboard at **http://localhost:8761**.
