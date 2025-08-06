**Linux System Hardening Project**
This project demonstrates how I used the Lynis Security Audit Tool to harden a Linux system by identifying and fixing vulnerabilities. The audit was performed on an Ubuntu Virtual Machine as part of my cybersecurity learning journey.

 **Objectives**
* Audit a Linux system using Lynis
* Identify security misconfigurations and weaknesses
* Apply hardening measures to secure the system
* Re-run Lynis to confirm fixes

 **Tools & Environment**
* Operating System:** Ubuntu VM (*CyberLABVM*) on VMware Workstation
* Security Tool:Lynis 3.0.3
* Firewall Utility:** UFW (*Uncomplicated Firewall*)

 **Initial Lynis Warnings & Fixes*
 
 **1. Outdated Lynis Version**
Warning:Version of Lynis is very old and should be updated `[LYNIS]`
Fix: Removed the old version and ran an audit with the updated one.

**Code:**
cd Downloads
cd lynis
sudo ./lynis audit system

 **2. Vulnerable Packages Detected**
Warning:Found one or more vulnerable packages `[PKGS-7392]`
Fix:Updated all packages to the latest versions.

**Code:**
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade

 **3. iptables Loaded Without Rules**
Warning: iptables module(s) loaded, but no rules active `[FIRE-4512]`
Fix:Enabled UFW and configured secure firewall rules.

**Code:**
sudo apt install ufw -y
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
sudo ufw enable

  **Post-Hardening Status**
After applying all the above fixes, I re-ran Lynis and confirmed:
* Lynis version is up-to-date
* No vulnerable packages found
* Firewall is active with strict rules

**References**
* Lynis Control References UFW Ubuntu Guide CISOfy GitHub Repo

**Author**
  Priyanka H S CyberSecurity Learner Hardening conducted using Lynis 3.0.3 on Ubuntu CyberLABVM.


