# Web Servers on EC2 (Apache & NGINX)

## Prerequisites
- **Security Group**: Inbound rule must allow **HTTP (Port 80)** and **HTTPS (Port 443)** traffic.

## Apache Web Server

### Commands (Amazon Linux / RHEL)
- Install & enable Apache:
  - `sudo yum update -y`
  - `sudo yum install httpd -y`
  - `sudo systemctl start httpd`
  - `sudo systemctl enable httpd`
- Serve a sample web page:
  - `echo "<h1>Hello from Apache on EC2</h1>" | sudo tee /var/www/html/index.html`

## NGINX Web Server

### Commands (Ubuntu / Debian)
- Install & enable NGINX:
  - `sudo apt update`
  - `sudo apt install nginx -y`
  - `sudo systemctl start nginx`
  - `sudo systemctl enable nginx`
- Serve a sample web page:
  - `echo "<h1>Hello from NGINX on EC2</h1>" | sudo tee /var/www/html/index.html`

## Management Commands
- Check status:
  - Apache: `systemctl status httpd`
  - NGINX: `systemctl status nginx`
- Restart web server:
  - Apache: `sudo systemctl restart httpd`
  - NGINX: `sudo systemctl restart nginx`

## Notes
- **Document Root**: Default directory for web pages is `/var/www/html`.
- **Test Access**: Open `http://<instance-public-ip>` in your browser.
- **Port Conflict**: Avoid running both on Port 80 simultaneously unless setting up NGINX as a reverse proxy.
