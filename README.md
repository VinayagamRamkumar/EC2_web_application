## EC2_web_application


#  Web application on AWS EC2  

This project demonstrates how I, as a **Cloud Engineer**, launched an **EC2 instance**, installed **Nginx**, deployed a static website, and accessed it using the public IP address.  

---

##  Project Screenshots  

### 1. EC2 Instances Running  
Launched two **EC2 instances** (`t2.micro`) in **N. Virginia (us-east-1)**.  
![EC2 Instances](images/ec2_instance.png)  

---

### 2. Editing index.html File  
Connected to the EC2 instance using **SSH (EC2 Instance Connect)** and created a custom `index.html` file.  
![Editing HTML File](images/index.html_for_web_application.png)  

---

### 3. Nginx Web Server Setup  
Replaced the default Nginx web page with the new `index.html` under `/usr/share/nginx/html/`.  
![Nginx Setup](images/nginx.code.png)  

---

### 4. Hosted Application Output  
Accessed the website using the **EC2 Public IPv4 address** in the browser.  
![Hosted Website](images/Output_web_application.png)  

---

##  Workflow  

1. **Launch EC2 Instance**  
   - Amazon Linux 2023 AMI  
   - Instance type: `t2.micro`  
   - Security Group → Allowed **SSH (22)** & **HTTP (80)**  

2. **Install & Configure Nginx**  
   ```bash
   sudo yum update -y
   sudo amazon-linux-extras enable nginx1
   sudo yum install nginx -y
   sudo systemctl start nginx
   sudo systemctl enable nginx

## Example index.html Code

<!DOCTYPE html>
<html>
<head>
    <title>MY TECHTRAPTURE</title> <br>
    <style>
        body {
            font-family: Arial, sans-serif;<br>
            margin: 0;<br>
            padding: 0;<br>
        }
        header {
            background-color: #2c3e50;<br>
            color: white;<br>
            padding: 20px;<br>
            text-align: center;<br>
            font-size: 24px;<br>
        }
        nav {
            text-align: center;<br>
            background: #34495e;<br>
            padding: 10px;<br>
        }
        nav a {
            color: white;<br>
            margin: 0 15px;<br>
            text-decoration: none;<br>
            font-weight: bold;<br>
        }
        section {
            padding: 20px;<br>
            text-align: center;<br>
        }
    </style>
</head>
<body>
    <header>
        MY TECHTRAPTURE<br>
    </header>
    <nav>
        <a href="#">Home</a><br>
        <a href="#">About</a><br>
        <a href="#">Services</a><br>
        <a href="#">Contact</a><br>
    </nav>
    <section>
        <h2>Welcome to my application hosted on AWS!</h2><br>
    </section>
</body>
</html>


## Final Output 
![Output](images/Output_web_application.png)