# **Student Lab Sheet -- Running a Python Flask App on AWS EC2 (Ubuntu + t2.micro)**

## **Lab Objective**

Deploy a simple Python Flask application on an **Ubuntu t2.micro EC2
instance**.\
You will learn how to: - Launch and connect to an EC2 Ubuntu instance\
- Install system updates, Python, and pip\
- Clone a GitHub repository\
- Install dependencies and run a Flask app\
- Access the application through the EC2 public IP

------------------------------------------------------------------------

# **1. Prerequisites**

-   AWS account\
-   SSH key pair to connect to EC2\
-   Basic Linux command knowledge

------------------------------------------------------------------------

# **2. Launch an EC2 Ubuntu Instance**

1.  Go to **AWS Console → EC2 → Launch Instance**\
2.  **Name:** `python-flask-lab`\
3.  **AMI:** **Ubuntu Server 22.04 LTS**\
4.  **Instance Type:** **t2.micro**\
5.  **Key Pair:** Create or choose an SSH key pair\
6.  **Networking:**
    -   Ensure **Auto-assign Public IP = Enabled**\
    -   Create/choose a **Security Group** with:
        -   **SSH (22)** → Your IP\
        -   **TCP (5000)** → Your IP or 0.0.0.0/0 (demo)\
7.  Launch the instance.

------------------------------------------------------------------------

# **3. Connect to the EC2 Ubuntu Instance**

``` sh
ssh -i <your-key>.pem ubuntu@<public-ip>
```

------------------------------------------------------------------------

# **4. Update System + Install Git, Python, and Pip**

``` sh
sudo apt update -y && \
sudo apt upgrade -y && \
sudo apt install -y git python3 python3-pip
```

------------------------------------------------------------------------

# **5. Clone the GitHub Repository + Install Dependencies**

``` sh
git clone https://github.com/bobbybabu007/gke-python-flask-sample-application.git && \
cd gke-python-flask-sample-application && \
pip3 install -r requirements.txt
```

------------------------------------------------------------------------

# **6. Run the Flask Application**

``` sh
python3 app.py
```

Expected output:

    Running on http://0.0.0.0:5000

------------------------------------------------------------------------

# **7. Access the Application**

Open:

    http://<public-ip>:5000

You should see:

    Learning DevOps with Python

------------------------------------------------------------------------

# **8. Lab Completion Checklist**

✔ Ubuntu t2.micro instance running\
✔ Public IP reachable\
✔ SSH connection successful\
✔ Git, Python3, pip installed\
✔ Repo cloned\
✔ Requirements installed\
✔ Flask app running\
✔ Browser shows the Flask message

------------------------------------------------------------------------

# **9. Cleanup (Optional)**

Terminate the instance:

**EC2 Console → Instances → Select instance → Instance state →
Terminate**

------------------------------------------------------------------------

# **End of Lab**

You have successfully deployed a Python Flask app on an Ubuntu EC2
instance.

## Try out similar app-stacks

1. https://github.com/bobbybabu007/gha-python-image-app
2. https://github.com/bobbybabu007/gha-python-django-image-generator-app
3. https://github.com/bobbybabu007/cicd-python-django-WebApp
4. https://github.com/Luko575/django-to-do-app