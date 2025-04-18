# Spring Boot Application - Jenkins CI/CD with WAR Deployment

This project demonstrates building a Spring Boot application and deploying it using Jenkins as a CI/CD pipeline. The artifact generated is a `.war` file, which can be deployed to a server such as Apache Tomcat.

---

## 🧰 Technologies Used

- Java 17/21
- Spring Boot Application
- Maven
- Jenkins
- GitHub
- Apache Tomcat (for WAR deployment)

---

## ✅ Assignment Checklist

- [x] Jenkins installed and configured
- [x] Spring Boot application packaged as `.war`
- [x] Jenkins job created and configured
- [x] WAR file deployed and application tested

---

## 📝 Steps to Follow

### 1. Jenkins Installation

- Download Jenkins from the [official Jenkins website](https://www.jenkins.io/download/)
- Install and start Jenkins on your local machine
- Access Jenkins at: `http://localhost:8080`
- Install necessary plugins:
  - Maven Integration Plugin
  - Git Plugin

---

### 2. Spring Boot Application Setup

- Created the Spring Boot application

- In the `pom.xml`, change the packaging type to `war`:

```xml
<packaging>war</packaging>
