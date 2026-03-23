![image](https://github.com/user-attachments/assets/33afd5da-baa9-4acc-86de-edf7cea6939c)
# 🌐 My Simple Website

Welcome to **My Simple Website** — a beginner-friendly project showcasing how to host a static website on an AWS EC2 instance using **Apache**, **Jenkins**, and **GitHub** for automated deployment 🚀.

## 🔗 Live Website

🌍 [http://3.7.65.80](http://3.7.65.80)

---

## 🛠️ Tech Stack

| Tool      | Purpose                          |
|-----------|----------------------------------|
| 🐧 Ubuntu | Operating System (on EC2)         |
| 🌐 Apache | Web Server                        |
| 🔧 Jenkins| CI/CD Automation                  |
| 🧠 GitHub | Version Control & Source Hosting |
| ☁️ AWS EC2| Cloud Hosting                     |

---

## 🚀 How It Works

1. 📝 Code is written and pushed to GitHub:  
   👉 [https://github.com/Jyoti9916/my-simple-website.git](https://github.com/Jyoti9916/my-simple-website.git)

2. 🔔 GitHub triggers a webhook to Jenkins on new commits.

3. 🤖 Jenkins pulls the latest code and deploys it to `/var/www/html` on the Apache server.

4. 🌐 The website updates automatically and is served via your EC2's public IP.

---

## ⚙️ Setup Instructions

### 📦 1. Update & Install Apache
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2
🧰 2. Install Git
bash
Copy
Edit
sudo apt install git -y
🧪 3. Install Jenkins
bash
Copy
Edit
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install openjdk-11-jdk -y
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
🔗 4. Connect GitHub Webhook to Jenkins
URL: http://3.7.65.80:8080/github-webhook/

Content type: application/json

Trigger: Just the push event

⚙️ 5. Jenkins Build Script (Freestyle job)
bash
Copy
Edit
cd /var/www/html
sudo rm -rf *
sudo git clone https://github.com/Jyoti9916/my-simple-website.git .



📌 Notes
Ensure EC2 Security Group allows traffic on port 80 (HTTP) and 8080 (Jenkins).

Jenkins admin password:

bash
Copy
Edit
sudo cat /var/lib/jenkins/secrets/initialAdminPassword

🙋‍♀️ Author
Jyoti
🔗 https://github.com/Jyoti9916
