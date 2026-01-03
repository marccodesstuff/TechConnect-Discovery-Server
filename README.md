# Discovery Server

Minimal Spring Boot Eureka Discovery Server used for local development and testing.

Key points:
- Spring Boot 3.x, Java 17
- Actuator enabled (health + info)
- Multi-stage Dockerfile for local builds
- Uses JDBC/Postgres config for services that expect a DB (DB not required by Eureka itself)

Usage:
- Build and run with Docker Compose:

  docker compose up --build
