# My Flask App with Docker and AWS

## Project Overview

This project showcases a simple Flask web application running inside a Docker container and deployed on AWS EC2. The application displays a basic greeting message when accessed through a web browser.

## Getting Started

### Prerequisites

Ensure you have the following installed on your local machine:

- [Docker](https://www.docker.com/get-started)
- [Git](https://git-scm.com/)

### Clone the Repository

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
Build and Run Locally
bash
Copy code
sudo docker build -t my-flask-app .
sudo docker run -p 5000:5000 my-flask-app
Visit http://localhost:5000 in your web browser to access the Flask app.

Deployment on AWS
Launch AWS EC2 Instance
Create an EC2 instance with Ubuntu.
Connect to the instance using SSH.
Install Docker on EC2 Instance
bash
Copy code
# Update package list
sudo apt update

# Install Docker dependencies
sudo apt install apt-transport-https ca-certificates curl software-properties-common

# Add Docker GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Add Docker repository
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io

# Add user to the docker group
sudo usermod -aG docker $USER

# Log out and log back in
Deploy Flask App on EC2
Copy your project files to the EC2 instance.
Build and run the Docker container on the EC2 instance.
bash
Copy code
sudo docker build -t my-flask-app .
sudo docker run -p 5000:5000 my-flask-app
Visit http://your-ec2-ip:5000 to access the Flask app.

Project Structure
app.py: The main Flask application file.
Dockerfile: Configuration file for building the Docker image.
README.md: Project documentation.
Notes
This project is intended for educational purposes.
Avoid using the development server in a production environment.
vbnet
Copy code

Replace placeholders like `your-username`, `your-repo`, and `your-ec2-ip` with your actual GitHub username, repository name, and the public IP address of your AWS EC2 instance.

This README provides a detailed guide on setting up the project
