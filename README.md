# 🛠️ Centralized Configuration Server

## 📋 Overview
This project is a **Spring Cloud Config Server** that centrally manages configuration files for multiple microservices in a distributed system. By externalizing configurations, you can change settings dynamically without redeploying applications, thus ensuring flexibility and scalability.

## 🚀 Features
- Centralized configuration management for multiple microservices.
- Supports **Git-based** configuration storage.
- Hot-reload configurations without restarting services.
- Profile-based configurations (e.g., `dev`, `test`, `prod`).
- Secure storage for sensitive properties using encryption.

## 🛠️ Tech Stack
- **Backend**: Java, Spring Boot, Spring Cloud Config
- **Version Control**: Git (for configuration storage)
- **Tools**: Docker (for containerization), Maven

## 📂 Project Structure
```bash
src
  main
    java
      com/example/configserver
        ConfigServerApplication
    resources
      application.properties
```

## 🔧 Setup Instructions

### 1. Prerequisites
- Java 17+
- Maven 3.8+
- Git (configured with your repository)
- Docker (optional, for containerization)

### 2. Clone the Repository
```bash
git clone https://github.com/truongnguyen-kt/spring-boot-config-server
cd config-server
```

### 3. Update Configuration Files
Make sure to update the application.properties files to point to your Git repository where configurations are stored.
```bash
spring.application.name=ConfigServer
server.port=8888
spring.cloud.config.server.git.uri=https://github.com/truongnguyen-kt/spring-boot-config-server
spring.cloud.config.server.git.clone-on-start=true
spring.cloud.config.server.git.default-label=main
management.endpoints.web.exposure.include=*
```

### 4. Build and Run
To run the server:
```bash
mvn clean install
mvn spring-boot:run
```
Alternatively, using Docker:
```bash
docker build -t config-server .
docker run -p 8888:8888 config-server
```
### 5. Accessing Configurations
You can access the configuration for a service as follows:
```bash
http://localhost:8888/{application}/{profile}
```

## 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing
Contributions are welcome! Please open an issue or submit a pull request.

## 📞 Contact
For any inquiries, please reach out to ngtruong166@gmail.com.
