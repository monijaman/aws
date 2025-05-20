# 📘 Nginx Setup on Ubuntu – Full Guide

This guide provides step-by-step instructions to install and configure **Nginx** on Ubuntu to serve files from `/var/www/html`.

## 🛠️ All-in-One Setup Script

```bash
# ---------------------------------------------------------
# 📋 Step 1: System Information
# ---------------------------------------------------------
cat /etc/os-release     # OS details
free -m                 # Memory info
lscpu                   # CPU info
df -h                   # Disk usage
ip a                    # Network interfaces

# ---------------------------------------------------------
# ⚙️ Step 2: Install Nginx
# ---------------------------------------------------------
sudo apt-get update
sudo apt-get install nginx -y

# ---------------------------------------------------------
# 🔍 Step 3: Test Nginx Installation
# ---------------------------------------------------------
nginx -t                # Check nginx config syntax
curl localhost          # Test nginx is serving default page

# ---------------------------------------------------------
# 📁 Step 4: Check Default Web Root
# ---------------------------------------------------------
sudo nginx -T | grep root
# Example output: root /usr/share/nginx/html;

# ---------------------------------------------------------
# 🏗️ Step 5: Create New Web Root Directory
# ---------------------------------------------------------
sudo mkdir -p /var/www/html
echo "<h1>Hello from Nginx on Ubuntu</h1>" | sudo tee /var/www/html/index.html

# ---------------------------------------------------------
# ✏️ Step 6: Update Nginx Server Block
# ---------------------------------------------------------
sudo nano /etc/nginx/conf.d/default.conf

# Paste the following inside the file:
# ---------------------------------------
# server {
#     listen 80;
#     server_name localhost;
#
#     root /var/www/html;
#     index index.html;
#
#     location / {
#           try_files $uri $uri/ =404;
#     }
# }
# ---------------------------------------

# ---------------------------------------------------------
# ✅ Step 7: Validate and Reload Nginx
# ---------------------------------------------------------
sudo nginx -t                  # Validate config
sudo systemctl reload nginx    # Apply changes
```


## show user metadata:

curl 169.254.169.254/latest/meta-data
curl -v -H "X-aws-ec2-metadata-token: $TOKEN" http://169.254.169.254/latest/meta-data/


## show all ebs list
lsblk
