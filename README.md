# Continuous Integration and Deployment Pipeline with Jenkins and Maven

This is a practice project for the integration of Maven with Jenkins for Continous Integration
## Tools and Technologies

- **Maven**: Build Tool
- **GitHub**: Source Control Management
- **Jenkins**: Continuous Integration and Continuous Deployment (CI/CD) Tool

## Project Setup

### Step 1: Jenkins Server Setup on Linux VM

1. **Create Ubuntu VM**: Provision an Ubuntu VM (t2.medium) using a cloud provider.
2. **Security Group Configuration**: Enable inbound traffic on port 8080.
3. **Connect to VM**: Use MobaXterm or another SSH client to connect to the VM.
4. **Install Java**:
   ```sh
   sudo apt update
   sudo apt install fontconfig openjdk-17-jre
   java -version
   ```

5. **Install Jenkins**:
   ```sh
   sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
     https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
     https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
     /etc/apt/sources.list.d/jenkins.list > /dev/null
   sudo apt-get update
   sudo apt-get install jenkins
   ```

6. **Start Jenkins**:
   ```sh
   sudo systemctl enable jenkins
   sudo systemctl start jenkins
   ```

7. **Verify Jenkins**:
   ```sh
   sudo systemctl status jenkins
   ```

8. **Access Jenkins**: Open a web browser and navigate to `http://<public-ip>:8080/`.

9. **Retrieve Jenkins Admin Password**:
   ```sh
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword
   ```

10. **Create Admin Account & Install Required Plugins**:
    - **Pipeline Types**:
      - **Declarative Pipeline**: Simplified syntax, standardized pipeline definitions.
      - **Scripted Pipeline**: Flexible, written in Groovy, suitable for complex scenarios.

### Step 2: Configure Maven as a Global Tool in Jenkins

1. Navigate to **Manage Jenkins** -> **Tools** -> **Maven Installation**.
2. Add Maven to the global tool configuration.

### Step 4: Create Jenkins Job

1. **Stage 1: Clone Git Repository**
2. **Stage 2: Build with Maven**
3. **Stage 3: Create Docker Image**
4. **Stage 4: Deploy Docker Container**

### Step 5: Trigger Jenkins Job

Run the Jenkins job to execute the CI/CD pipeline.

### Step 6: Configure Security Group

Enable the necessary ports in the security group to allow external access.

### Step 7: Access Application

Open a web browser and navigate to `http://<public-ip>:<port>/` to access the application.


## Conclusion

This project showcases the end-to-end process of Continous Integration(CI) with the use of Jenkins and Maven.
