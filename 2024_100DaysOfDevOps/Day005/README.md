# Day 5: Automation with Shell Scripts

## Objectives
- Learn to automate repetitive tasks using shell scripts.
- Write scripts to automate system administration tasks.
- Schedule automated tasks using cron jobs.

## Topics Covered
1. Identifying Tasks for Automation
2. Writing Automation Scripts
3. Scheduling Tasks with Cron
4. Automating System Administration
5. Automating File Management
6. Automating Backups and Updates

## Learning Plan (1-2 Hours)

### Identifying Tasks for Automation
1. **Understanding Task Automation** (10 minutes)
    - Identify tasks that can be automated using shell scripts.
    - **Notes:**
        - 

### Writing Automation Scripts
2. **Creating Automation Scripts** (20 minutes)
    - Write a script to automate a simple task, such as creating directories and files.
        ```sh
        #!/bin/bash
        for dir in {1..5}; do
            mkdir "dir$dir"
            touch "dir$dir/file$dir.txt"
        done
        ```
    - **Notes:**
        - 

### Scheduling Tasks with Cron
3. **Using Cron for Scheduling** (20 minutes)
    - Write a cron job to schedule the automation script.
        ```sh
        crontab -e
        # Add a job to run the script every day at midnight
        0 0 * * * /path/to/your/script.sh
        ```
    - **Notes:**
        - 

### Automating System Administration
4. **Automating System Tasks** (15 minutes)
    - Write scripts to automate system updates and maintenance tasks.
        ```sh
        #!/bin/bash
        sudo apt-get update && sudo apt-get upgrade -y
        ```
    - **Notes:**
        - 

### Automating File Management
5. **Automating File Handling Tasks** (15 minutes)
    - Write scripts to automate file backups and cleanups.
        ```sh
        #!/bin/bash
        tar -cvf /backup/backup.tar /important/data
        find /tmp -type f -mtime +7 -exec rm {} \;
        ```
    - **Notes:**
        - 

### Automating Backups and Updates
6. **Automating Backups** (20 minutes)
    - Write a script to automate regular backups and updates.
        ```sh
        #!/bin/bash
        tar -cvf /backup/backup_$(date +%F).tar /important/data
        sudo apt-get update && sudo apt-get upgrade -y
        ```
    - **Notes:**
        - 

## Hands-On Exercises (1 Hour)

### Exercise 1: Automate File Creation (20 minutes)
- Write a script to automate the creation of directories and files.
- **Notes:**
    - 

### Exercise 2: Schedule a Script with Cron (20 minutes)
- Schedule the script from Exercise 1 to run at a specific time using cron.
- **Notes:**
    - 

### Exercise 3: Automate System Maintenance (20 minutes)
- Write and schedule a script to automate system updates and cleanups.
- **Notes:**
    - 

### Evening Review
7. **Review and Reflect** (10 minutes)
    - Summarize what you've learned about automation with shell scripts.
    - Reflect on any challenges faced during hands-on exercises and how to overcome them.
    - Plan for the next day’s topic: Introduction to Kubernetes (K8s) and its Architecture.
    - **Notes:**
        - 
