---
title: "Linux System Administration & Automation"
datePublished: Tue Apr 29 2025 12:56:43 GMT+0000 (Coordinated Universal Time)
cuid: cma2ih8tg000908lbf4ce8dz1
slug: linux-system-administration-and-automation
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1745931394335/543017a7-6074-492f-ad4f-bbf964efca76.png
tags: linux, linux-for-beginners, linux-commands

---

LINUX SYSTEM ADMINISTRATION & AUTOMATION 👨‍💻  
  
Diving deep into Linux system administration and automation. I learned how to manage users, secure access, monitor processes, handle disk volumes, and most importantly automate repetitive tasks using shell scripting.

Here’s a quick look at what I explored 👇

✅ what i learned & did this week: Created & managed Linux users and groups (w/ sudo + SSH restrictions)

Set secure file permissions in a shared workspace

Used awk, grep, and sed to analyze real log data

Mounted volumes and monitored disk usage

Managed & killed background processes

Wrote a shell script to automate backups (cron scheduled!)

🛠️ project: Linux server monitoring & automation I imagined myself as a DevOps engineer managing production servers monitoring logs, analyzing user access, automating backup scripts. It really helped solidify my understanding of how Linux powers modern infrastructure.

🧠 key takeaway: Mastering Linux isn’t just about knowing commands it’s about building automation mindset, knowing how to troubleshoot fast, and keeping systems secure and efficient. That’s what DevOps is all about! 🚀

📘 step-by-step guide & commands

1. user & group management
    

`sudo useradd devops_user sudo groupadd devops_team sudo usermod -aG devops_team devops_user sudo passwd devops_user sudo usermod -aG sudo devops_user sudo nano /etc/ssh/sshd_config # Add: DenyUsers test_user sudo systemctl restart sshd`

2. file & directory permissions
    
    `mkdir /devops_workspace touch /devops_workspace/project_notes.txt chmod 740 /devops_workspace/project_notes.txt ls -l /devops_workspace`
    
3. log file analysis
    

`wget` [`https://github.com/sample-repo/Linux_2k.log grep`](https://github.com/sample-repo/Linux_2k.log%EF%BF%BCgrep) `"error" Linux_2k.log awk '{print $1, $2, $3}' Linux_2k.log sed -E 's/[0-9]+.[0-9]+.[0-9]+.[0-9]+/[REDACTED]/g' Linux_2k.log > sanitized.log awk '{print $5}' Linux_2k.log | sort | uniq -c | sort -nr | head -10`

4\. volume management

`mkdir /mnt/devops_data sudo mount /dev/sdb1 /mnt/devops_data # or use loop device for local df -h mount | grep devops_data`

5. process management
    

`ping` [`google.com`](http://google.com) `> ping_test.log & ps aux | grep ping top htop kill`

6. automate backups with shell script
    

`sudo vim backup_`[`script.sh`](http://script.sh)  
Content:

`#!/bin/bash BACKUP_NAME="backup_$(date +%F).tar.gz" tar -czf /backups/$BACKUP_NAME /devops_workspace echo -e "\e[32mBackup Successful: $BACKUP_NAME\e[0m"`

`chmod +x backup_`[`script.sh`](http://script.sh) `crontab -e # Add: 15 16 * /path/to/backup_`[`script.sh`](http://script.sh)

#90DaysOfDevOps #DevOps #Linux #SysAdmin #Automation #ShellScripting #InfraAsCode #CloudComputing #LinuxAdmin #ITCareer #DevOpsEngineer #LinkedInLearning #TechJourney #CareerGrowth
