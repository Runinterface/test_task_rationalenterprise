## Test task!

### Documentation

Ansible Windows.
It is not included in `ansible-core`. To check whether it is installed, run `ansible-galaxy` collection list.

To install it, use: `ansible-galaxy collection install ansible.windows` on your ansible host.
Setup `winrm quickconfig` on Windows host, and `python v.3.12.4`.

### You can set custom variable:<br>

domain_name: default - `test.local`<br>
ssl_directory: default - `C:\ssl\`<br>
openssl_version: default- `3_3_1`<br>
nginx_path: default - `C:\nginx\`<br>
nginx_version: default - `1.26.1`<br>
wsw_version: default - `2.12.0`<br>

Password for vault secret value: `1234`

### Start:

```bash

ansible-playbook playbooks/test.yml -i inventories/test_env --extra-vars="ansible_host=YOUR_HOST_IP ansible_port=5985 ansible_password=YOUR_PASSWORD ansible_user=YOUR_USERNAME" --ask-vault-pass

```
> :warning:  **Don't forget that the `test.local` domain is not a real domain. Add a domain to your /etc/hosts/**

### Goal
```
Test Assignment: Setting Up a Web Server on Windows Using Ansible
Goal:
Configure an Nginx web server on a Windows host using Ansible, including generating self-signed certificates, installing the necessary certificates on the system, configuring Nginx to work over HTTPS, and ensuring secrets management using Ansible Vault.
Steps:
 1. Generate Self-Signed Certificates:
 ◦ Generate a root self-signed certificate (CA certificate).
 ◦ Generate a server certificate signed by the root certificate.
 ◦ Install the root certificate in the "Trusted Root Certification Authorities" of the local machine on the Windows host.
 2. Install and Configure Nginx as a Service:
 ◦ Install Nginx on the Windows host using WinSW (Windows Service Wrapper) to manage Nginx as a service.
 ◦ Add necessary firewall permissions for Nginx to allow incoming connections on HTTP and HTTPS ports.
 3. Configure Nginx to Work Over HTTPS:
 ◦ Configure Nginx to use the previously created certificates to ensure the web server works over HTTPS.
 4. Secrets Management:
 ◦ Use Ansible Vault to securely store and manage sensitive data such as passwords and private keys.
Expected Result:
After completing all steps, Nginx should be installed and running as a service on the Windows host, configured to work over HTTPS using self-signed certificates. Secrets should be securely managed using Ansible Vault.
Additional Requirements:
 • Store the results in a GitHub repository.
 • Include a README file with all prerequisites and a link to the repository.
This task ensures a secure and automated setup of a web server with proper management of sensitive information.
```
