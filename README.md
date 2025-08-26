## EC2_web_application

##  Project Overview
This project demonstrates how to deploy a **static web application** on an **Amazon EC2 instance** using **Nginx** as the web server.  
It covers launching an EC2 instance, installing Nginx, hosting a static website, and accessing it via a public IP.

---

## Tools & Services Used
- **AWS EC2** – Virtual server to host the web app  
- **Amazon Linux 2023** – OS for the instance  
- **Nginx** – Web server for serving static content  
- **HTML & CSS** – For building the frontend UI  
- **SSH** – Secure connection to EC2  

---

## Steps Followed

### 1️⃣ Launching an EC2 Instance
- Logged in to **AWS Console → EC2 → Launch Instance**  
- Selected **Amazon Linux 2023 AMI**  
- Chose **t2.micro (Free Tier)**  
- Allowed inbound rules for **HTTP (80)** and **SSH (22)**  

 **EC2 Instance Running**  
![EC2 Instance](images/ec2%20instance.png)

---

### 2️⃣ Installing Nginx
Connected via SSH and ran:

```bash
sudo yum update -y
sudo amazon-linux-extras enable nginx1
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx
----


## example index.html code

<!DOCTYPE html>
<html>
<head>
    <title>My Web Application</title>
    <style>
        header {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 24px;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
        }
        nav a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>

    <header>
        <h1>MY TECHTRAPTURE</h1>
        <nav>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#services">Services</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <p>Welcome to my application hosted on AWS!</p>

</body>
</html>



## Final Output
![Output](images/Output%20for%20ec2%20in%20web%20application.png)