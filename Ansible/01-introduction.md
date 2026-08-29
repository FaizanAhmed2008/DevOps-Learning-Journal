# Ansible Introduction & Concepts

## What is Ansible?
- Open-source **Configuration Management** and **Automation** tool.
- **Agentless**: Operates over SSH; no extra client software needed on target nodes.
- **Idempotent**: Re-running playbooks applies only necessary changes to achieve desired state.

## Key Concepts
- **Control Node**: The machine where Ansible is installed and executed.
- **Managed Nodes**: The target servers managed by Ansible via SSH.
- **Inventory**: File (`hosts` or `inventory.ini`) defining hostnames/IPs of managed nodes.
- **Modules**: Built-in reusable units of code executed on managed nodes (e.g., `apt`, `service`, `file`, `copy`).
- **Playbook**: YAML file containing one or more plays defining automation tasks.

## Installation & Setup

### Install Ansible (Control Node)
- Ubuntu / Debian:
  - `sudo apt update`
  - `sudo apt install ansible -y`
- Verify installation:
  - `ansible --version`

## Ad-Hoc Commands (Quick Tasks)
- Test connectivity (ping all hosts):
  - `ansible all -m ping -i inventory.ini`
- Run a shell command on all webservers:
  - `ansible webservers -m command -a "uptime" -i inventory.ini`
- Install a package via ad-hoc command:
  - `ansible webservers -m apt -a "name=curl state=present" --become -i inventory.ini`

## Notes
- Uses SSH keys for authentication.
- `--become` grants elevated (sudo) privileges.
