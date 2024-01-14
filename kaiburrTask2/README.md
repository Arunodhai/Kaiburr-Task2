
# Kaiburr Task 2 Spring Boot API Docker Image

This repository contains the Dockerfile and instructions for building a Docker image for the Kaiburr Spring Boot API application(created in task 1).

## Docker Image Details

- **Base Image:** OpenJDK 21
- **Exposed Port:** 8080
- **Entrypoint:** `java -jar kaiburr.jar`

## Build Instructions

To build the Docker image for the Kaiburr Spring Boot API, follow these steps:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/your-repository.git
   cd your-repository
2. **Build the Docker Image:**
   ```bash
   docker build -t kaiburr-api:latest .

3. **Run the Docker Container:**
   ```bash
   docker run -p 8080:8080 kaiburr-api
