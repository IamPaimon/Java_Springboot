# Java_Springboot
# 🐾 Spring Boot PetClinic Deployment using Jenkins

This repository demonstrates the deployment of the [Spring Boot PetClinic](https://github.com/spring-projects/spring-petclinic) application using **Jenkins** on a **Linux-based environment**. The project includes CI/CD automation, Java setup, and verification through browser access.

---

## 🚀 Project Highlights

- 🧩 Spring Boot Application: PetClinic v3.5.0
- ☕ Java: OpenJDK 21
- 🔧 Jenkins: Installed and Configured
- 📦 Maven: Used for building the project
- 📍 Hosted on: Ubuntu Linux Server (GCP VM)
- 🌐 Application URL: Accessible via `http://<your-ip>:8083`

---

## 📸 Setup Snapshots

| Description                | Screenshot |
|----------------------------|------------|
| Java Version Installed     | ![Java Version](./assets/java-Version.png) |
| JDK 21 Installed           | ![JDK Installation](./assets/JDK_installation.png) |
| Jenkins Unlock Screen      | ![Jenkins Unlock](./assets/Jenkins_Host.png) |
| Jenkins GPG Key Setup      | ![Jenkins Key](./assets/Jenkins_Key.png) |
| Jenkins Ready Screen       | ![Jenkins Ready](./assets/Jenkins_Ready.png) |
| Jenkins Repo Setup         | ![Jenkins Repo](./assets/Jenkins-repo-to-system.png) |
| Linux Hosted Application   | ![Linux Host App](./assets/Linux_Host_App.png) |
| VM Hosted PetClinic        | ![VM Host App](./assets/VM_Host_App.png) |
| Localhost Spring App       | ![Localhost PetClinic](./assets/Localhost_Petclinic.png) |

> 📂 You can upload these screenshots to a folder named `assets` in your repo for proper linking.

---

## 🛠️ Setup Steps

### 1. Install Java 21
sudo apt-get update
sudo apt install openjdk-21-jdk -y
java --version


### 2. Install Jenkins
   sudo apt-get update
sudo apt install -y wget gnupg
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key

echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/" | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

sudo apt-get update -y
sudo apt-get install jenkins -y


### 3. Start Jenkins
 sudo systemctl start jenkins
sudo systemctl enable jenkins
Visit http://<your-ip>:8080 and unlock Jenkins using:
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword

### 🔧 Build and Deploy ### 
After Jenkins is configured, use a Freestyle project or Pipeline job to:

Pull the PetClinic source from GitHub

Build it with Maven: mvn clean package

Run the JAR:  java -jar target/spring-petclinic-3.5.0-SNAPSHOT.jar --server.port=8083


### 🌍 Final Output ### 
Access the running PetClinic app on:  http://<your-server-ip>:8083


### ✅ Conclusion
You’ve successfully set up a full CI/CD pipeline for a Spring Boot application using Jenkins and Maven on a Linux VM. This setup is ideal for DevOps automation, CI/CD practice, and cloud deployment learning.




