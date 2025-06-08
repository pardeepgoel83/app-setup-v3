# vpn-multiapp-ansible

This project provides an Ansible playbook setup for hosting multiple applications on a VPN server. It includes a WordPress setup for **app-gudliving** and a Docker-based deployment for **app-ledger**. The directory structure is modular and reusable, making it easy to manage and extend.

## Project Structure

```
vpn-multiapp-ansible
├── group_vars
│   └── all.yml                # Global variables for all hosts
├── host_vars
│   └── vpn_server.yml         # Variables specific to the VPN server
├── inventories
│   └── production              # Inventory file for production environment
├── playbooks
│   ├── main.yml               # Main playbook for orchestrating deployments
│   ├── wordpress.yml          # Playbook for setting up WordPress
│   └── docker_app.yml         # Playbook for deploying Docker applications
├── roles
│   ├── common
│   │   ├── tasks
│   │   │   └── main.yml       # Common tasks for all hosts
│   │   └── templates           # Common configuration templates
│   ├── vpn
│   │   ├── tasks
│   │   │   └── main.yml       # Tasks for setting up the VPN server
│   │   └── templates           # VPN server configuration templates
│   ├── wordpress
│   │   ├── tasks
│   │   │   └── main.yml       # Tasks for installing and configuring WordPress
│   │   ├── templates           # WordPress configuration templates
│   │   └── vars
│   │       └── main.yml       # Default variables for WordPress role
│   └── docker_app
│       ├── tasks
│       │   └── main.yml       # Tasks for deploying Docker applications
│       ├── templates           # Docker configuration templates
│       └── vars
│           └── main.yml       # Default variables for Docker application role
```

## Setup Instructions

1. **Clone the Repository**: Clone this repository to your local machine.
   
   ```bash
   git clone <repository-url>
   cd vpn-multiapp-ansible
   ```

2. **Configure Inventory**: Update the inventory file located in `inventories/production` with your server details.

3. **Set Variables**: Modify the variable files in `group_vars/all.yml` and `host_vars/vpn_server.yml` to suit your environment.

4. **Run the Playbook**: Execute the main playbook to set up the VPN server and deploy the applications.

   ```bash
   ansible-playbook -i inventories/production playbooks/main.yml
   ```

## Usage Guidelines

- Use the `playbooks/wordpress.yml` to specifically set up the WordPress application.
- Use the `playbooks/docker_app.yml` to deploy Docker-based applications.
- Customize roles and tasks as needed to fit your specific requirements.

## Contributing

Feel free to submit issues or pull requests to improve this project. Contributions are welcome!

cd d:\Projects\app-setup-v3\vpn-multiapp-ansible
ansible-playbook -i inventories/production playbooks/main.yml
ansible-playbook -i inventories/production playbooks/main.yml -u your_ssh_user
ansible-playbook -i inventories/production playbooks/main.yml -u your_ssh_user --private-key=path\to\your\key.pem


ssh -i /home/key.pem your_user@157.173.220.220



ssh-keygen -t rsa -b 4096 -f /home/key.pem

chmod 600 /home/key.pem

ssh-copy-id -i /home/key.pem.pub root@your_server_ip
