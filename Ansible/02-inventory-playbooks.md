# Ansible Inventory & Playbooks

## Inventory File Example (`inventory.ini`)

```ini
[webservers]
web1 ansible_host=54.210.12.34
web2 ansible_host=54.210.12.35

[dbservers]
db1 ansible_host=10.0.1.50

[all:vars]
ansible_user=ubuntu
ansible_ssh_private_key_file=~/.ssh/my-key.pem
```

## Playbook Example (`webserver.yml`)

```yaml
---
- name: Configure Web Server
  hosts: webservers
  become: true

  tasks:
    - name: Ensure NGINX is installed
      apt:
        name: nginx
        state: present
        update_cache: yes

    - name: Deploy custom index page
      copy:
        content: "<h1>Managed by Ansible</h1>"
        dest: /var/www/html/index.html
        mode: '0644'

    - name: Ensure NGINX is running and enabled
      service:
        name: nginx
        state: started
        enabled: yes
```

## Commands
- Run playbook:
  - `ansible-playbook -i inventory.ini webserver.yml`
- Check playbook syntax:
  - `ansible-playbook --syntax-check webserver.yml`
- Perform dry run (simulate execution without making changes):
  - `ansible-playbook -i inventory.ini webserver.yml --check`
- View hosts in inventory:
  - `ansible-inventory -i inventory.ini --list`

## Notes
- **YAML indentation**: Must use spaces (not tabs) for consistent structure.
- **`become: true`**: Runs tasks as `root` user via sudo.
- **`state: present` / `state: absented`**: Declarative state management.
