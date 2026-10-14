# AWS Application Load Balancer & EC2 Web Server Project

This project demonstrates how to set up an **Application Load Balancer (ALB)** on AWS across multiple **Ubuntu EC2 instances** to achieve high availability and traffic distribution.

---

## 🚀 Step 1: Launching Ubuntu EC2 Instances
1. Logged into the **AWS Management Console** and navigated to the **EC2 Dashboard**.
2. Launched two **Ubuntu EC2 Instances** (Server 1 and Server 2) in different Availability Zones.
3. Configured **Security Groups** to allow inbound HTTP traffic on Port `80` and SSH on Port `22`.

---

## 💻 Step 2: Setting up Web Servers on Ubuntu
Connected to the Ubuntu instances via SSH and set up a lightweight HTTP server using Python:
1. Created an HTML file (`index.html`) featuring an Amazon-style UI layout.
2. Started the Python web server in the background:
   ```bash
   python3 -m http.server 80
   ⚖️ Step 3: Configuring the Application Load Balancer (ALB)
Went to EC2 > Load Balancers and created an Internet-facing Application Load Balancer (aws-demo-ho-lb).

Created a Target Group (aws-tg) and registered both Ubuntu EC2 instances into it.

Configured health checks to ensure traffic is routed only to healthy instances.
🔄 Step 4: Testing Load Balancing
Accessed the Load Balancer DNS URL to verify traffic distribution.

Refreshing the page dynamically switches between Server 1 and Server 2, verifying successful load balancing.
