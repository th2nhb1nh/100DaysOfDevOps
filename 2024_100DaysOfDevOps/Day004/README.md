# Day 4: Automation with Shell Scripts

- [Day 4: Automation with Shell Scripts](#day-4-automation-with-shell-scripts)
  - [Objectives](#objectives)
  - [Topics Covered](#topics-covered)
  - [Learning Plan (1-2 Hours)](#learning-plan-1-2-hours)
    - [Automating Repetitive Tasks](#automating-repetitive-tasks)
    - [Managing Files and Directories](#managing-files-and-directories)
    - [Network Automation](#network-automation)
    - [User and Permission Management](#user-and-permission-management)
    - [Error Handling and Notifications](#error-handling-and-notifications)

## Objectives
- Automate repetitive tasks using shell scripts.
- Learn to schedule and manage automated scripts.
- Understand how to handle files and directories programmatically.

## Topics Covered
1. Automating Repetitive Tasks
2. Managing Files and Directories
3. Network Automation
4. User and Permission Management
5. Error Handling and Notifications

## Learning Plan (1-2 Hours)

### Automating Repetitive Tasks
1. **Automating Common Tasks** (15 minutes)
    - Write scripts to automate daily tasks like backups, updates, and report generation.
      - Back-up script:
        ```sh
        #!/bin/bash
        src="path/to/src"
        des="path/to/des/date_$(date +%Y%m%d).tar.gz"
        tar -czvf $des $src
        echo "Backup completed at $des"
        ```
      - Update script:
        ```sh
        #!/bin/bash
        sudo apt update && sudo apt upgrade -y
        echo "System updated"
        ```

### Managing Files and Directories
2. **File and Directory Automation** (20 minutes)
    - Write scripts to manage files and directories.
        ```sh
        # Create a directory if it doesn't exist
        [ ! -d /path/to/dir ] && mkdir -p /path/to/dir

        # Move files older than 7 days to an archive
        find /path/to/files -type f -mtime +7 -exec mv {} /path/to/archive/ \;

        # you can also use cron job to schedule for the task
        * * * * * find /path/to/files -type f -mtime +7 -exec mv {} /path/to/archive/ \;
        ```

### Network Automation
3. **Automating Network Tasks** (15 minutes)
    - Write scripts for network-related tasks like ping tests and bandwidth monitoring.
        ```sh
        # Ping a list of hosts
        for host in google.com yahoo.com bing.com; do
            ping -c 4 $host > /dev/null && echo "$host is reachable" || echo "$host is not reachable"
        done
        ```
    - **Notes:**
        - Use `curl` or `wget` for HTTP requests and downloads.

### User and Permission Management
4. **Automating User and Permission Tasks** (20 minutes)
    - Write scripts to automate user and permission management.
        ```sh
        # Create a new user and set a password
        useradd newuser
        echo "newuser:password" | chpasswd

        # Set permissions on a directory
        chown -R newuser:newuser /path/to/dir
        chmod -R 755 /path/to/dir
        ```
    - **Notes:**
        - Manage user accounts and permissions programmatically.
        - Ensure security by setting appropriate permissions.

### Error Handling and Notifications
5. **Handling Errors and Sending Notifications** (20 minutes)
    - `||` operator: OR: if cmd1 failed, run cmd2, else, exit.
        ```sh
        cmd1 || cmd2
        ```
    - Implement error handling and send notifications for script failures.
        ```sh
        # Check if a command succeeds, if not send an email
        command || echo "Command failed" | mail -s "Script Error" user@example.com

        # Log errors (if have) to a file 
        command 2>> error.log
        ```
    - **Notes:**
        - Use logging and notifications to monitor script execution.
        - Handle errors gracefully and provide useful feedback.
