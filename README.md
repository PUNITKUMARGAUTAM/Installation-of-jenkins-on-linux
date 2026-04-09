🚀 Installation of Jenkins on Linux (AWS EC2)

This project demonstrates the step-by-step installation of Jenkins on a Linux server (Ubuntu) hosted on AWS EC2.

📌 Prerequisites
AWS Account
EC2 Instance (Ubuntu)
SSH Key (.pem file)
Basic knowledge of Linux commands
⚙️ Step 1: Connect to EC2 Instance

First, create an EC2 instance and connect to it using SSH:

cd Downloads
ssh -i "docker-vm.pem" ubuntu@ec2-18-60-222-35.ap-south-2.compute.amazonaws.com
☕ Step 2: Install Java (Required for Jenkins)

Jenkins requires Java to run:

sudo apt update
sudo apt install -y fontconfig openjdk-21-jre
java -version
📦 Step 3: Install Jenkins (LTS Version)
Add Jenkins Key
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
Add Jenkins Repository
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
Install Jenkins
sudo apt update
sudo apt install -y jenkins
🔍 Step 4: Verify Jenkins Installation
jenkins --version

Example Output:

2.541.3
🌐 Step 5: Access Jenkins UI
Copy your EC2 Public IP
Open port 8080 in AWS Security Group
Open in browser:
http://<your-public-ip>:8080

Example:

http://18.60.222.35:8080/
🔐 Step 6: Unlock Jenkins

Retrieve the initial admin password:

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

Copy the password and paste it into the Jenkins UI.

⚡ Step 7: Setup Jenkins
Click Install Suggested Plugins
Wait for plugin installation
Create Admin User (Username, Password, Email)
Save and Continue
🎯 Step 8: Jenkins Dashboard

After successful setup, you will be redirected to the Jenkins dashboard.

📸 Screenshot

✅ Conclusion

You have successfully installed and configured Jenkins on AWS EC2 (Linux) and accessed it via browser.



📌 Notes
Ensure port 8080 is open in the security group
Always keep your .pem file secure
Use sudo where required
