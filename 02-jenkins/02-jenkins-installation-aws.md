# Jenkins Installation on AWS (EC2)

This section explains how to install Jenkins on an AWS EC2 instance.

---

## Architecture used

- EC2 instance for Jenkins Controller
- Security Group allowing required ports
- IAM role for AWS access (recommended)

---

## Step 1: Launch EC2 Instance

- Choose Ubuntu or Amazon Linux
- Instance type: t2.micro (Free Tier)
- Storage: Default is sufficient

---

## Step 2: Configure Security Group

Allow:
- Port 22 for SSH
- Port 8080 for Jenkins UI

---

## Step 3: Connect to EC2

    ssh -i your-key.pem ubuntu@<public-ip>

---

## Step 4: Install Java

Jenkins requires Java.

    sudo apt update
    sudo apt install openjdk-17-jdk -y

Verify:

    java -version

---

## Step 5: Install Jenkins

Add Jenkins repository and install:

    curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null

    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null

    sudo apt update
    sudo apt install jenkins -y

---

## Step 6: Start Jenkins

    sudo systemctl start jenkins
    sudo systemctl enable jenkins

Check status:

    sudo systemctl status jenkins

---

## Step 7: Access Jenkins UI

Open browser:

    http://<EC2-Public-IP>:8080

Get initial admin password:

    sudo cat /var/lib/jenkins/secrets/initialAdminPassword

---

## Step 8: Initial Setup

- Paste admin password
- Install suggested plugins
- Create admin user

Jenkins is now ready for use.

---

## Important Notes

- Do not expose Jenkins publicly without security
- Use IAM roles instead of AWS keys
- Backup Jenkins configuration regularly
