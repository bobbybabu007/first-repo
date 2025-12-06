# Task 2: Deploying React Movie Catalog App on AWS EC2

This task guides students through deploying the **reactjs‑moviecatalog‑app** on an EC2 instance.

---

## **1. Launch an EC2 Instance**
### **Instance Requirements**
- **Amazon Linux 2023** or **Ubuntu 22.04**
- Instance type: **t2.micro** (Free‑tier)
- Storage: **8–16 GB**
- Security group:
  - Allow **SSH (22)** from your IP
  - Allow **HTTP (80)** from anywhere

---

## **2. Connect to the EC2 Instance**

```bash
ssh -i your-key.pem ec2-user@ec2-public-ip
```

For Ubuntu:

```bash
ssh -i your-key.pem ubuntu@ec2-public-ip
```

---

## **3. Install Node.js and Git**

For **Amazon Linux / RHEL**:

```bash
sudo dnf install -y nodejs npm git
```

For **Ubuntu**:

```bash
sudo apt update
sudo apt install -y nodejs npm git
```

---

## **4. Clone the Repository**

```bash
git clone https://github.com/faniabdullah/reactjs-moviecatalog-app.git
cd reactjs-moviecatalog-app
```

---

## **5. Install Packages**

```bash
npm install
```

---

## **6. Build and Run the App**

### **Option A – Development Server**
```bash
npm start
```
App runs on port **8080**  
Visit: `http://EC2-Public-IP:8080`

---

### **Option B – Production Build**
```bash
npm run build
```

Serve the `/dist` folder:

```bash
npm install -g serve
serve -s dist -l 8080
```

---

## **7. Keep App Running After Logout (Optional)**

```bash
sudo npm install -g pm2
pm2 start "npm start"
pm2 startup
pm2 save
```

---

## **End of Task 2**

## Try out similar app-stacks

1. React app - https://github.com/aditya-sridhar/simple-reactjs-app
2. Angular app - https://github.com/kwangsing3/movie-tv-viewer
3. React+Redux - https://github.com/Rhymond/product-compare-react
