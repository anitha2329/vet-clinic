# Vet Clinic Application

A customized Spring Boot backend application built using Maven, based on the Spring PetClinic architecture. This repository serves as the core API framework for the Vet Clinic ecosystem.

## 🚀 Getting Started

### Prerequisites
Before running the application, make sure you have the following installed:
* **Java 17** or newer (Full JDK)
* **Maven** (or use the provided wrapped executable `./mvnw`)

### Running Locally
To launch the application using the embedded Maven wrapper, run the following command in your terminal:

```bash
./mvnw spring-boot:run
```

Once started, the backend application will be accessible locally at:
👉 **http://localhost:8080**

---

## 📦 Containerization & Deployment

### Building a Container Image
You can compile and build a local Docker container image directly through the Spring Boot build plugin (requires a running Docker daemon):

```bash
./mvnw spring-boot:build-image
```

### Running the Container
Locate the compiled image and run it locally mapping the server port:

```bash
docker run -p 8080:8080 docker.io/library/spring-petclinic:latest
```

---

## 💾 Database Profiles
By default, the application runs using an **in-memory H2 database**. The database resets every time the server restarts. 

To use a persistent relational database management system, activate a specific Spring profile during runtime:

* **MySQL:** `spring.profiles.active=mysql`
* **PostgreSQL:** `spring.profiles.active=postgres`

### Spinning up local databases with Docker Compose:
```bash
# Start MySQL instance
docker compose up mysql

# Start PostgreSQL instance
docker compose up postgres
```

---

## 🛠️ Project Structure & Architecture

* **Main Application Class:** `PetClinicApplication.java`
* **Configuration & Properties:** `src/main/resources/application.properties`
* **Styles & Assets:** Core styles are managed through `.scss` sheets located inside `src/main/resources/static/resources/css`. If modified, recompile the stylesheets using the Maven active profile: `./mvnw package -P css`.
