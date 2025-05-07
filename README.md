# 📝 MERN Blog Application

A full-stack blogging web app powered by the **MERN stack (MongoDB, Express, React, Node.js)**, integrated with **AWS S3** for image hosting, and **PM2** for backend process management.

---
###  Folder Structure

```bash
renad-blog-app/

├── backend/ # Express.js backend API
├── frontend/ # React.js frontend
├── README.md
└── .env.example # Sample environment variables

```
###  Future Improvements

```bash
- Create, read, update, and delete blog posts
- RESTful API built with Express and MongoDB
-  Responsive frontend built with React + Vite
- Deployed on AWS (EC2, S3, IAM, Route 53, etc.)
- Environment configuration with `.env`


```

###  Technologies Used

```bash
- **Frontend**: React, Vite, Tailwind CSS
- **Backend**: Node.js, Express, MongoDB, Mongoose
- **Deployment**: AWS EC2, S3, Route 53, PM2, NGINX
- **CI/CD**: Manual via CLI and AWS SDK
- **Tools**: VS Code, Postman, GitHub, pnpm

```
##  Project Overview

This is a fully functional blog platform that allows users to:

-  Create and manage blog posts
-  Upload and display images via AWS S3
-  Register and authenticate with JWT
-  View a responsive UI built with React & Vite

The project follows a modern DevOps deployment pipeline using PM2 and AWS infrastructure.

---

##  Architecture Flow

Here’s how data flows through the app:

1. **Client (React)** sends API requests using Axios to the backend.
2. **Backend (Node.js + Express)** handles the logic, connects to **MongoDB**, and manages blog data.
3. For image uploads:
   - Client uploads the image → API → **AWS S3** stores the image.
   - The backend returns the public S3 URL to the frontend to be displayed.
4. Backend process is managed with **PM2**, ensuring auto-restart on crash and persistence on reboot.
5. Optional: You can deploy the backend using **ALB (Application Load Balancer)** with an **Auto Scaling Group (ASG)** in a cloud-native setup for horizontal scaling.

---

##  Sample Screenshot

![screenshot](https://renad-blogapp-frontend.s3.eu-north-1.amazonaws.com/images/image.jpeg)
![screenshot](https://renad-blogapp-frontend.s3.eu-north-1.amazonaws.com/images/my-photo.png.jpeg)
---


##  How to Run Locally

### . Clone the Repository

```bash
git clone https://github.com/cw-barry/blog-app-MERN.git
cd blog-app-MERN
```
###  Backend Setup

```bash
cd backend
cp .env.example .env
pnpm install
pnpm run dev
```
###  Environment Variables:
Add a .env file in your backend/ folder:

```bash
PORT=5000
MONGO_URI=your_mongo_connection
JWT_SECRET=your_secret_key
AWS_ACCESS_KEY_ID=your_aws_key
AWS_SECRET_ACCESS_KEY=your_aws_secret
S3_BUCKET_NAME=your_bucket_name
S3_REGION=eu-north-1
```
Make sure your MongoDB URI is set correctly in .env.

###   Setup Frontend:


```bash
cd ../frontend
pnpm install
pnpm run dev

```
Visit the app at http://localhost:5173
###  Deployment (AWS)

```bash
Frontend: Deployed on S3 Bucket
Example URL:
http://renad-blogapp-frontend.s3-eu-north-1.amazonaws.com/

Backend: Running on EC2 Instance with PM2 and NGINX
Access via:
http://<your-ec2-public-ip>:5000


```

Make sure the frontend is configured to communicate with the correct backend API URL.

###  Traffic Flow (Architecture Overview):


```bash
User → Route 53 (optional) → ALB → EC2 (backend)
         ↳ S3 Static Hosting (frontend)

```

###  Tech Stack

```bash
Tech Stack
Frontend: React, Vite, TailwindCSS

Backend: Node.js, Express, JWT, Multer

Database: MongoDB Atlas

DevOps: PM2, AWS S3, (Optional: ALB + ASG)

Others: PowerShell (for upload), dotenv


```
###  Screenshots:


```bash

✅ S3 Static Website URL working & curl -I response shows 200 OK  file name :200 OK

✅ pm2 list screenshot showing backend running   file name :PM2 status

✅ Uploaded image to S3 and accessed via public URL  file name : Upload an image

```

