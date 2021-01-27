# ANSIBLE101

configure ansible.cfg file

[defaults]
inventory = ./hosts 
# Use local hosts file in folder 
forks = 3
# limit Ansible to connect to 1 device at a time for pretty output
timeout = 20
# increase SSH timeout to 20 seconds for remote connections
host_key_checking = False
# Don't worry about RSA Fingerprints
retry_files_enabled = False 
# Do not create .retry files on job failure




---
# Playbook to Backup Cisco Config 

- hosts: CSR-Routers
  connection: network_cli
  gather_facts: false

  tasks:
   - name: Show Run on Device
     ios_command:
       commands:
         - show run
     register: config

   - name: Save output to /backups
     copy:
       content: "{{config.stdout[0]}}"
       dest: "./backups/{{inventory_hostname}}-backup.txt"
       
       
       
       sudo rpm -Va
       sudo apt-get upgrade
       ansible version
       sudo yum install ansible -y
       sudo vi /etc/hostname
       
       
       ip addr
       
       ansible-playbook -i hosts main.yml --check

nnb
