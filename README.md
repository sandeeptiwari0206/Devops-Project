# Title: Node Project

# Objectives : Using this code retriving the system information (Uptime and cpu load).

# Requirements : 

- OS : Ubuntu 24 LTS
- Packages : docker , node , NPM , PM2
- 
# Setup : 

Follow the below script to install required packages.
~~~
#!/bin/bash

# Exit on any error
set -e

echo "Step 1: Update and Upgrade Ubuntu Packages..."
sudo apt update && sudo apt upgrade -y

echo "Step 2: Install Git..."
sudo apt install -y git

echo "Step 3: Install Docker..."
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo systemctl status docker --no-pager

echo "Step 4: Install Node.js and npm..."
sudo apt install -y nodejs npm

echo "Step 5: Install PM2 globally..."
sudo npm install -g pm2

echo "Step 6: Clone the Node.js project from GitHub..."
cd /tmp
git clone https://github.com/sandeeptiwari0206/node-project.git
cd node-project

echo "Step 7: Install required Node.js dependencies..."
npm install

# Optional: install additional modules if not in package.json
npm install express os-utils

echo "Step 8: Start the Node.js app with PM2..."
pm2 start server.js
pm2 save
pm2 startup | sudo tee /tmp/pm2-startup.sh > /dev/null
sudo bash /tmp/pm2-startup.sh

echo "Step 9: Display PM2 status..."
pm2 list

echo "✅ Node.js project is now running with PM2 and set to auto-start on boot."
~~~

## Run the script

-Give the permission to the script to run

~~~
chmod +x node_packages.sh
./node_packages.sh
~~~


# Result
