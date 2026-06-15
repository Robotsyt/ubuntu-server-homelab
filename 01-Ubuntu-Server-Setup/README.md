# Ubuntu Server Home Lab – SSH, Firewall, and Apache Deployment

Project Type: Home Lab – Systems Administration  
Operating System: Ubuntu Server LTS  
Technologies: Ubuntu Server, SSH, UFW Firewall, Apache2, Git, GitHub, VS Code  

------------------------------------------------------------
PROJECT OVERVIEW
------------------------------------------------------------
This project demonstrates the setup of a secure Ubuntu Server environment, including SSH access, firewall configuration, system updates, and Apache web server deployment. The goal was to simulate real-world Linux system administration tasks and build a portfolio-ready infrastructure project.

------------------------------------------------------------
1. SYSTEM UPDATE & INITIAL SETUP
------------------------------------------------------------

sudo apt update
sudo apt upgrade -y

Install required packages:

sudo apt install git apache2 ufw -y

Purpose:
- Update system packages
- Install Git for version control
- Install Apache for web hosting
- Install UFW for firewall management

------------------------------------------------------------
2. SSH VERIFICATION (BEFORE FIREWALL CHANGES)
------------------------------------------------------------

Check SSH service status:

sudo systemctl status ssh

Test SSH connection:

ssh username@server-ip

Verification steps:
- Confirm SSH service is active
- Confirm port 22 is reachable
- Confirm remote login works before firewall activation

------------------------------------------------------------
3. FIREWALL CONFIGURATION (UFW SETUP)
------------------------------------------------------------

Enable firewall:

sudo ufw enable

Allow SSH:

sudo ufw allow OpenSSH

Allow web traffic:

sudo ufw allow 80/tcp
sudo ufw allow 443/tcp

Check firewall status:

sudo ufw status verbose

Outcome:
- Firewall activated successfully
- SSH access preserved
- Web ports opened for Apache

------------------------------------------------------------
4. APACHE WEB SERVER INSTALLATION
------------------------------------------------------------

Install Apache:

sudo apt install apache2 -y

Start Apache:

sudo systemctl start apache2

Enable Apache on boot:

sudo systemctl enable apache2

Check status:

sudo systemctl status apache2

------------------------------------------------------------
5. APACHE TROUBLESHOOTING
------------------------------------------------------------

Check logs:

journalctl -xe

Restart Apache:

sudo systemctl restart apache2

Check port usage:

sudo lsof -i :80

Resolution:
- Identified service or port conflict
- Restarted Apache successfully
- Restored web server functionality

------------------------------------------------------------
6. CUSTOM PORT CONFIGURATION (8090)
------------------------------------------------------------

Allow port through firewall:

sudo ufw allow 8090/tcp

Edit Apache config:

sudo nano /etc/apache2/ports.conf

Add line:

Listen 8090

Restart Apache:

sudo systemctl restart apache2

Verify port:

sudo ss -tuln | grep 8090

------------------------------------------------------------
7. FINAL SYSTEM VALIDATION
------------------------------------------------------------

Check firewall:

sudo ufw status

Check SSH:

ssh username@server-ip

Check Apache:

systemctl status apache2

Check open ports:

sudo ss -tuln

------------------------------------------------------------
FINAL OUTCOME
------------------------------------------------------------
- Secure SSH remote access configured
- UFW firewall enabled and hardened
- Apache web server successfully deployed
- Custom port 8090 configured
- System stability verified after changes

------------------------------------------------------------
SKILLS DEMONSTRATED
------------------------------------------------------------
- Linux system administration
- SSH remote access management
- Firewall configuration (UFW)
- Web server deployment (Apache2)
- Service troubleshooting (systemctl, journalctl)
- Network port configuration
- Basic server hardening practices
