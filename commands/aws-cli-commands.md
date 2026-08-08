# AWS CLI Commands

## 1. Check AWS CLI Version

```bash
aws --version
```

Used to verify that AWS CLI is installed correctly.

---

## 2. Configure AWS CLI

```bash
aws configure
```

Used to configure AWS credentials, default region, and output format.

---

## 3. Verify AWS Identity

```bash
aws sts get-caller-identity
```

Used to verify the AWS identity currently being used by the CLI.

---

## 4. List S3 Buckets

```bash
aws s3 ls
```

Used to list available S3 buckets.

---

## 5. Upload File to S3

```bash
aws s3 cp test.txt s3://<bucket-name>/
```

Used to upload a file from the EC2 server to an S3 bucket.

---

## 6. Download File from S3

```bash
aws s3 cp s3://<bucket-name>/test.txt .
```

Used to download a file from S3 to the EC2 server.

---

## 7. List Files in an S3 Bucket

```bash
aws s3 ls s3://<bucket-name>/
```

Used to view files stored inside a specific S3 bucket.
