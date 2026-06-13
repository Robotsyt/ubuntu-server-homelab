# Ubuntu Server Home Lab

## Overview

This repository documents the implementation of a Linux-based home lab designed to strengthen practical Systems Administration skills. The project focuses on deploying and managing an Ubuntu Server while following administrative practices commonly used in enterprise environments.

Throughout this project, I configured secure remote administration using SSH, verified and managed firewall rules with UFW, installed and configured Apache, deployed a website from GitHub, and resolved real-world service and networking issues through structured troubleshooting.

Rather than simply completing configuration tasks, every step was documented to create a repeatable deployment process and serve as a reference for future infrastructure projects.

---

# Objectives

* Deploy an Ubuntu Server environment
* Configure secure remote administration using SSH
* Verify system packages and security updates
* Configure and validate the UFW firewall
* Install and configure the Apache web server
* Deploy a website using Git and GitHub
* Troubleshoot service failures and networking issues
* Document each phase of implementation

---

# Environment

| Component        | Details                      |
| ---------------- | ---------------------------- |
| Operating System | Ubuntu Server LTS            |
| Remote Access    | SSH                          |
| Firewall         | UFW (Uncomplicated Firewall) |
| Web Server       | Apache2                      |
| Version Control  | Git & GitHub                 |
| Shell            | Bash                         |

---

# Technologies Used

* Ubuntu Server
* Linux CLI
* SSH
* UFW Firewall
* Apache2
* Git
* GitHub
* Bash

---

# Skills Demonstrated

* Linux System Administration
* Remote Server Management
* Firewall Configuration
* Service Management
* Network Troubleshooting
* Apache Administration
* Git-Based Deployments
* Root Cause Analysis
* Technical Documentation

---

# Project Implementation

## 1. Ubuntu Server Setup

The server was installed with Ubuntu Server LTS and updated to ensure all operating system packages and security patches were current before additional software was installed.

Administrative tasks included:

* Updating package repositories
* Installing system updates
* Verifying package integrity
* Installing foundational utilities such as Git for future deployments

---

## 2. SSH Remote Administration

Remote administration was configured using SSH to allow secure command-line management from another workstation.

Before enabling the firewall, SSH access was verified to ensure remote connectivity would not be interrupted during firewall activation.

---

## 3. Firewall Configuration

The UFW firewall was configured to restrict unnecessary network access while allowing required services.

Firewall tasks included:

* Verifying SSH access
* Allowing SSH through the firewall
* Enabling UFW
* Confirming firewall status
* Opening TCP port 8090 for Apache after resolving a port conflict

---

## 4. Apache Web Server

Apache was installed to host a personal portfolio website.

During deployment, Apache failed to start because another service was already using the default web server port. After identifying the conflict, Apache was reconfigured to use port 8090 and normal operation was restored.

---

## 5. GitHub Deployment

Git was configured with a global username and email before connecting the server to GitHub.

The portfolio repository was cloned directly into Apache's document root, allowing website updates to be deployed through Git version control rather than manual file transfers.

---

## 6. Troubleshooting

Throughout the project, several real-world administrative issues were encountered and resolved.

| Issue                            | Resolution                                                                                   |
| -------------------------------- | -------------------------------------------------------------------------------------------- |
| Apache service failed to start   | Reviewed system logs using `systemctl` and `journalctl` to identify the root cause.          |
| Port conflict                    | Identified Docker (CasaOS) using port 8080 and reconfigured Apache to use port 8090.         |
| Deferred service restart message | Confirmed this was expected Ubuntu behavior during package installation.                     |
| Firewall verification            | Verified SSH remained accessible before enabling UFW and confirmed firewall rules afterward. |
| Git configuration                | Configured Git identity before committing changes.                                           |
| Initial Git push failed          | Created the initial commit before pushing to GitHub.                                         |
| Nested Git repository            | Removed the nested repository and recommitted from the correct project root.                 |
| Website deployment               | Verified repository permissions and ownership after deployment to Apache.                    |

---

# Key Accomplishments

By completing this project I successfully:

* Built an Ubuntu Server from a minimal installation
* Configured secure SSH administration
* Verified and enabled a Linux firewall
* Installed and configured Apache
* Deployed a website directly from GitHub
* Diagnosed and resolved service startup failures
* Resolved networking and port conflicts
* Created a repeatable deployment workflow
* Documented each stage of implementation

---

# Lessons Learned

This project emphasized the importance of following a structured troubleshooting methodology rather than making configuration changes through trial and error.

Each issue was approached by verifying service status, reviewing logs, validating firewall rules, checking network ports, and identifying the root cause before implementing a solution. This approach reduced unnecessary configuration changes while improving confidence in diagnosing Linux server issues.

The project also reinforced best practices for documentation, version control, and repeatable deployments, all of which are essential skills in Systems Administration.

---

# Future Roadmap

Planned additions to this home lab include:

* Windows Server Administration
* Active Directory
* Group Policy
* DNS & DHCP
* Docker Containers
* System Monitoring
* Bash Automation
* PowerShell Automation
* Scheduled Tasks (cron)
* SSL/HTTPS Configuration
* Virtual Hosts
* Network Services

---

# Conclusion

This repository represents the foundation of my Systems Administration portfolio.

The project demonstrates practical experience configuring and managing an Ubuntu Server while applying structured troubleshooting, secure remote administration, firewall management, web server deployment, and Git-based workflows.

As the home lab continues to grow, this repository will expand to include Windows Server, Active Directory, automation, monitoring, and additional enterprise technologies that reflect the responsibilities of a modern Systems Administrator.
