# AWS EC2 + IAM + S3 Integration Using AWS CLI ☁️🚀

## 📌 Project Overview

This project demonstrates how to connect an **Ubuntu EC2 instance with Amazon S3** using the **AWS CLI** and **IAM authentication**.

The goal was to gain hands-on experience with AWS infrastructure, Linux server management, IAM authentication, AWS CLI, and S3 file operations.

---

## 🏗️ Architecture

```text
                    Local Machine
                         │
                         │ SSH Authentication
                         │
                    PEM Key Pair
                         │
                         ▼
                 ┌─────────────────┐
                 │   AWS EC2       │
                 │ Ubuntu Server   │
                 └────────┬────────┘
                          │
                          │ AWS CLI
                          │ IAM Authentication
                          ▼
                 ┌─────────────────┐
                 │   Amazon S3     │
                 │     Bucket      │
                 └─────────────────┘
```

---

## 🛠️ AWS Services Used

* **Amazon EC2** – Hosted the Ubuntu Linux server
* **AWS IAM** – Managed authentication and permissions
* **Amazon S3** – Stored and retrieved files
* **AWS STS** – Verified AWS identity
* **AWS CLI** – Interacted with AWS services from the EC2 terminal

---

## 🚀 Implementation

### 1. Launch EC2 Instance

Created an Ubuntu EC2 instance and configured the required security group for SSH access.

The EC2 instance was used as the Linux server from which AWS CLI commands were executed.

---

### 2. Connect to EC2 Using SSH

Connected to the Ubuntu EC2 instance using the EC2 key pair.

```bash
chmod 400 key.pem

ssh -i key.pem ubuntu@<EC2-PUBLIC-IP>
```

> Replace `<EC2-PUBLIC-IP>` with the public IP address of your EC2 instance.

---

### 3. Install AWS CLI

Installed and configured AWS CLI on the Ubuntu server.

After installation, verified the AWS CLI:

```bash
aws --version
```

### 4. Configure AWS Authentication

Configured AWS credentials using:

```bash
aws configure
```

The configuration requires:

```text
AWS Access Key ID
AWS Secret Access Key
Default Region
Output Format
```

---

### 5. Verify IAM Identity

Verified which AWS identity was being used:

```bash
aws sts get-caller-identity
```

This helped confirm that the EC2 server was successfully authenticated with AWS.

---

### 6. Connect EC2 with Amazon S3

Listed available S3 buckets:

```bash
aws s3 ls
```

This verified that the EC2 server could communicate with Amazon S3.

---

### 7. Upload File to S3

Created or selected a file on the EC2 instance and uploaded it to S3:

```bash
aws s3 cp <file-name> s3://<bucket-name>/
```

Example:

```bash
aws s3 cp test.txt s3://my-demo-bucket/
```

---

### 8. Retrieve File from S3

Downloaded a file from S3 back to the EC2 instance:

```bash
aws s3 cp s3://<bucket-name>/<file-name> .
```

Example:

```bash
aws s3 cp s3://my-demo-bucket/test.txt .
```

---

## 📸 Project Screenshots

### EC2 Instance



### SSH Connection



### AWS CLI Configuration



### STS Identity Verification



### S3 Bucket


### File Upload



### File Download



---

## 📚 Key Learnings

Through this project, I gained practical experience with:

* EC2 instance provisioning
* Ubuntu/Linux server management
* SSH authentication using PEM key pairs
* AWS CLI installation and configuration
* IAM authentication and permissions
* AWS STS identity verification
* Amazon S3 bucket operations
* Uploading and downloading files using AWS CLI
* Troubleshooting AWS permission and access issues
* Understanding how AWS services communicate with each other

---

## 🔐 Security Considerations

During the project, I learned the importance of protecting AWS credentials.

**Never commit the following to GitHub:**

```text
*.pem
.aws/
credentials
config
.env
Access Keys
Secret Keys
```

A `.gitignore` file can be used to prevent accidentally uploading sensitive files.

---

## 🎯 What This Project Demonstrates

This project demonstrates a basic but important Cloud/DevOps workflow:

```text
Provision Infrastructure
        ↓
Configure Linux Server
        ↓
Authenticate with AWS
        ↓
Use AWS CLI
        ↓
Access S3
        ↓
Upload / Download Data
```

It helped me understand how AWS services can be integrated through the command line and provided practical experience with **Cloud Infrastructure, IAM, Linux, AWS CLI, and S3**.

---

## 🚀 Future Improvements

Possible improvements for this project include:

* Replace IAM access keys with an **EC2 IAM Role**
* Automate the EC2 setup using a shell script
* Use S3 bucket policies and least-privilege permissions
* Enable S3 versioning
* Add CloudWatch monitoring
* Automate file uploads using a CI/CD pipeline
* Provision the infrastructure using Terraform

---

## 👨‍💻 Author

**Kshitiz Rohilla**

B.Tech Computer Science
Cloud & DevOps Enthusiast

---

⭐ If you found this project useful, feel free to explore the repository.
