# Connecting to AWS EC2 via SSH

## Prerequisites
- **Key Pair File**: The `.pem` file downloaded when launching the instance.
- **Public IP / DNS**: The public IP address or IPv4 DNS of your EC2 instance.
- **Security Group**: Inbound rule must allow **SSH (Port 22)** traffic.

## Commands
- Set key file permissions (required by SSH client):
  - `chmod 400 <key-name>.pem`
- Connect to instance:
  - `ssh -i <path-to-key.pem> <username>@<public-ip-or-dns>`

### Example
```bash
ssh -i ~/.ssh/my-key.pem ubuntu@54.210.12.34
```

## Default Usernames by OS
- **Amazon Linux 2 / 2023**: `ec2-user`
- **Ubuntu**: `ubuntu`
- **CentOS**: `centos`
- **Debian**: `admin`
- **RHEL**: `ec2-user` or `root`

## Notes & Troubleshooting
- **Unprotected private key error**: Fix with `chmod 400 <key-name>.pem`.
- **Connection timed out**: Check if Security Group allows inbound traffic on Port 22 from your IP.
- **Permission denied (publickey)**: Ensure correct OS username and matching key pair are used.
