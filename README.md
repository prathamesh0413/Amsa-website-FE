🌟 Amsa Website Full Stack Project

Amsa Website is a full-stack web application with React frontend and Node.js backend, fully deployed on AWS EC2, served via CloudFront CDN, with an automated CI/CD pipeline and real-time monitoring dashboards with alerts.

🚀 Features

⚡ Fast Frontend: React ensures optimized performance and fast builds.

🔧 Backend API: Node.js + Express handles data processing, API requests, and business logic.

🛠️ CI/CD Pipeline: Fully automated deployment using GitHub Actions.

🌍 CloudFront CDN: Serves frontend assets globally for low latency and high availability.

📊 Monitoring & Alerts: Tracks server health, performance, and sends notifications.

☁️ AWS EC2 Hosting: Both frontend and backend hosted on EC2 instances.

🔐 HTTPS Support: SSL certificates configured for secure communication.

🗂 Project Structure
Amsa-Website/
├── CloudFormation/         # AWS infrastructure templates
├── frontend/               # React frontend
├── backend/                # Node.js + Express backend
├── .github/workflows/      # CI/CD pipeline
└── README.md               # Project documentation

🛠️ Tech Stack
Component	Technology
Frontend	React
Backend	Node.js, Express
Hosting	AWS EC2
CDN	AWS CloudFront
CI/CD	GitHub Actions
Monitoring	AWS CloudWatch / Custom Dashboards
Security	HTTPS / SSL Certificates
🏗️ Architecture Overview

Explanation:

GitHub Actions: Automates build, test, and deployment for frontend & backend.

EC2 Instances: Hosts frontend and backend.

CloudFront: Caches frontend assets for fast global delivery.

Monitoring: Tracks backend performance and triggers alerts on issues.

📦 Deployment Process
1️⃣ CloudFormation (Infrastructure as Code)

Creates EC2 instances for frontend and backend.

Sets up security groups, ports, and networking.

Configures CloudFront distribution for frontend.

Ensures repeatable and scalable infrastructure.

2️⃣ CI/CD Pipeline (GitHub Actions)

Triggers: On push to main branch

Frontend Steps:

Install dependencies

Run tests

Build production-ready code

Deploy build to EC2 frontend instance

Backend Steps:

Install dependencies

Run tests

Deploy backend to EC2 using pm2

Ensures automatic deployment and reduces manual errors.

3️⃣ Monitoring & Alerts

Tracks CPU, memory, network usage on EC2 instances.

Sends alerts via email or Slack for downtime or errors.

Ensures quick troubleshooting and uptime maintenance.

4️⃣ Frontend & Backend Deployment

Frontend:

cd frontend
npm install
npm run build
# Copy build to EC2
scp -r dist/ ubuntu@<FRONTEND_EC2_IP>:/var/www/html


Backend:

cd backend
npm install
# Copy backend to EC2
scp -r ./ ubuntu@<BACKEND_EC2_IP>:/home/ubuntu/backend
# SSH into EC2 and start server
ssh ubuntu@<BACKEND_EC2_IP>
cd backend
pm2 start index.js --name backend


CloudFront & HTTPS:

Configure CloudFront to serve frontend build files.

Attach SSL certificate for HTTPS.

🌐 Demo URLs

Frontend (HTTPS): https://<FRONTEND_EC2_IP>

Backend API (HTTPS): https://<BACKEND_EC2_IP>
(Replace <FRONTEND_EC2_IP> and <BACKEND_EC2_IP> with your EC2 public IPs or CloudFront URL.)

💻 Quick Setup Guide
# Clone repository
git clone https://github.com/<your-github-username>/amsa-website.git
cd amsa-website

# Frontend
cd frontend
npm install
npm run dev      # Development
npm run build    # Production

# Backend
cd ../backend
npm install
npm start        # Development
pm2 start index.js --name backend  # Production

# Configure CloudFront and SSL certificate
# GitHub Actions handles automatic deployment for future updates

🏷️ Badges

React • Node.js • GitHub Actions • AWS

📄 License

MIT License