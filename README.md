# Spring Boot WAR Deployment with Jenkins CI/CD (Windows Guide)

## Project Overview

This documentation explains how to configure a Spring Boot application for WAR deployment and set up a Jenkins pipeline for automated builds and deployments on Windows systems.

## Spring Boot WAR Configuration

### Packaging Configuration

To prepare the Spring Boot application for WAR deployment, modify your project's build configuration file. Change the packaging type to WAR by updating the packaging property.

### Servlet Container Dependency

Include the Tomcat starter dependency with a `"provided"` scope in your project dependencies.

### Application Class Modification

Extend your main application class from Spring Boot's servlet initializer class.

## Jenkins Pipeline Setup

### Prerequisites

Before configuring Jenkins, ensured the following steps:

* Jenkins installed and running on your Windows machine
* Java Development Kit (JDK) properly configured
* Apache Maven installed and available in system PATH
* Git client installed for source code management

### Jenkins Job Configuration
- configured Jenkins UI at: http://localhost:8082
1.  Create a new freestyle project in Jenkins
2.  Configure source code management to connect to your Git repository
3.  Set up build triggers according to your requirements
4.  Add a build step to execute Maven goals for clean package
5.  Configure post-build actions for WAR file deployment

### Deployment Configuration

Set up a post-build action to copy the generated WAR file from your project's target directory to Tomcat's webapps directory using a Windows batch script.

## Environment Setup
🧰 Environment Setup
-Apache Tomcat
-Install Apache Tomcat
-Configured Apache TomCatServer at port http://localhost:8080/


Add the following to conf/tomcat-users.xml:

xml
Copy
Edit
<role rolename="manager-script"/>
<user username="admin" password="admin" roles="manager-script"/>

### Tomcat Server

Install Apache Tomcat on your Windows machine and configure appropriate user roles for deployment. The `manager-script` role is required for automated deployments.



## Verification Steps

After pipeline execution:

1.  Check Jenkins console output for build success
2.  Verify WAR file appears in Tomcat's web applications directory
3.  Access your application through the configured Tomcat port

## Troubleshooting

### Common issues occured while implementing:

* Permission errors during file copy operations
* Port conflicts with other services
* Dependency resolution problems
* Deployment failures in Tomcat

## Screenshots

 <img width="960" alt="image" src="https://github.com/user-attachments/assets/2ea2df2d-7e22-4c95-be03-786d7fd03a0a" />

![Screenshot 2025-04-18 130310](https://github.com/user-attachments/assets/ed2b1e0d-9fae-4a88-89f1-a7024f7fc36d)

![Screenshot 2025-04-18 130333](https://github.com/user-attachments/assets/93ca08c7-39f2-4ee0-8465-2d99813ab0a6)

![Screenshot 2025-04-18 130534](https://github.com/user-attachments/assets/00a0678b-78a1-47ef-b11a-0916604403e4)

![Screenshot 2025-04-18 134305](https://github.com/user-attachments/assets/e0297d7b-301b-49f7-9e22-67fda3c043f8)

![Screenshot 2025-04-18 134748](https://github.com/user-attachments/assets/e4bba5af-79cd-4f91-af7f-230169919bb2)

![Screenshot 2025-04-18 134826](https://github.com/user-attachments/assets/b37c0838-1904-455d-87d5-1b84d9a0dc10)

