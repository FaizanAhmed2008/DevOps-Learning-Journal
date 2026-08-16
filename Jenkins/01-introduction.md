# Jenkins Introduction & Setup

## What is Jenkins?
- Open-source automation server used for **CI/CD** (Continuous Integration & Continuous Delivery).
- Automates building, testing, and deploying software projects.

## Key Concepts
- **Controller (Master)**: Manages the environment, schedules jobs, and serves the UI.
- **Agent (Node)**: Worker machine/container that executes build tasks assigned by the controller.
- **Job / Project**: A configured automated task (e.g., Freestyle project, Pipeline).
- **Plugins**: Addons that extend Jenkins functionality (e.g., Git, Docker, Kubernetes, Slack).

## Quick Setup

### 1. Prerequisites (Java Runtime)
- Install Java (required by Jenkins):
  - `sudo apt update`
  - `sudo apt install openjdk-17-jre -y`

### 2. Run with Docker (Fastest way)
- Run Jenkins container:
  - `docker run -d -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts`

### 3. Service Commands (Native Install)
- Check status:
  - `sudo systemctl status jenkins`
- Start / Restart Jenkins:
  - `sudo systemctl start jenkins`
  - `sudo systemctl restart jenkins`
- Unlock Jenkins (Initial Admin Password):
  - `sudo cat /var/lib/jenkins/secrets/initialAdminPassword`

## Notes
- **Default Port**: Jenkins runs on port `8080` (access via `http://<ip-address>:8080`).
- **Security**: Inbound port `8080` must be open in firewall / AWS Security Group.
