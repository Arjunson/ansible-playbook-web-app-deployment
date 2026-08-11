# Ansible Nginx Static Website Deployment

A simple Ansible project to install Nginx and deploy a static HTML website on a production server.

## Project Structure

    .
    ├── hosts.ini
    ├── playbook.yml
    ├── index.html
    └── README.md

## Requirements

- Ansible installed
- Ubuntu/Debian server
- SSH access
- `.pem` private key

## Inventory

In the host file:

    [prd]
    prd-server ansible_host=YOUR_SERVER_IP

    [prd:vars]
    ansible_user=ubuntu
    ansible_ssh_private_key_file=~/.ssh/your-key.pem
    ansible_port=22

## Run

Test the server connection:

    ansible -i hosts.ini prd -m ping

Run the playbook:

    ansible-playbook -i hosts.ini playbook.yml

## What It Does

- Installs Nginx
- Starts Nginx
- Enables Nginx on boot
- Deploys `index.html` to `/var/www/html`

## Access Website

Open the following in your browser:

    http://YOUR_SERVER_IP
