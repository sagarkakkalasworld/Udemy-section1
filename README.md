# 🚀 Deploying a Sample React App on AWS EC2 with Nginx

This guide helps you deploy a sample React application on an **AWS EC2** instance using **Nginx**.

---

## ✅ Configuration for this Project

🎥 [Launch an AWS EC2 instance (YouTube Guide)](https://youtu.be/ZbYn7TwFgko)

Once your EC2 instance is up and running, SSH into it and follow the steps below.

---

## 🧰 Install Git

```bash
sudo apt install git
````

Use any sample React project. You can clone the below project:

```bash
git clone https://github.com/sagarkakkalasworld/Udemy-section1.git
```

---

## ⚙️ Build Prerequisites

```bash
sudo apt update
sudo apt install nodejs
node --version

sudo apt install npm
npm --version
```

---

## 🚧 Build React Project

```bash
cd Udemy-section1
npm install
ls
npm run build
```

> **Note:** The build process may take some time. Warnings can be safely ignored.

---

## 🌐 Deploy Prerequisites

```bash
sudo apt install nginx
nginx -version

sudo cp -R build/ /var/www/html/
sudo vi /etc/nginx/sites-available/default
```

Edit the `root` path in the configuration file from:

```nginx
root /var/www/html;
```

to

```nginx
root /var/www/html/build;
```

Then restart Nginx:

```bash
sudo systemctl restart nginx
sudo systemctl status nginx
```

---

## 🌍 Application Visibility

* Go to **AWS EC2 → Security Groups**
* Under **Inbound Rules**, allow **Port 80 (HTTP)**

Now access your app using:

```text
http://<AWS Public IP>:80
```

---

## 🌐 Domain Visibility (Optional)

If you have a domain (e.g., from GoDaddy):

1. Log into GoDaddy
2. Go to **My Products → Domain → DNS**
3. In **A Records**, paste your **AWS EC2 public IP**

You can now access your React app via your custom domain.

---

## ⚠️ Notes

* When an EC2 instance is **stopped and started**, its **public IP changes**. Update your DNS accordingly.
* To avoid this, use an **Elastic IP** and associate it with your instance.
* The site may show **"Not Secure"** if **SSL is not configured**.

🔐 For free SSL configuration, refer to:
👉 [SSL Certificate Configuration – DevOps Must Know](https://www.sagarkakkalasworld.com/2024/06/devops-must-know-concepts-ssl.html)

---

## 🙋‍♂️ Connect with Me

* 🌐 [YouTube - Sagar Kakkala's World](https://www.youtube.com/@sagarkakkala)
* 💼 [LinkedIn - Sagar Kakkala](https://www.linkedin.com/in/sagar-kakkala)
* 📝 [Sagar Kakkala Blog](https://www.sagarkakkalasworld.com/p/contents-of-blog-sagar-kakkalas-world.html)
* 🔗 [Sagar Kakkala One Stop](https://linktr.ee/sagar_kakkalas_world)


---

Let me know if you want this uploaded to a GitHub repo or want badges/images added.
```
