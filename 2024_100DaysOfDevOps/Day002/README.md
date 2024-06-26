# Day 2: Advanced Linux Command-Line Operations and Scripting

## Objectives
- Master advanced Linux command-line operations.
- Write advanced shell scripts to automate tasks.
- Learn to manage system resources and processes efficiently.

## Topics Covered
1. Advanced Shell Commands
    - File manipulation
    - Process management
    - Networking commands
2. Bash Scripting
    - Functions and loops
    - Conditionals
    - Input/output handling
3. Practical Automation
    - Automating common tasks
    - Scheduling tasks with cron jobs

## Learning Plan (1-2 Hours)

### Introduction
- Brief overview of advanced Linux command-line operations and scripting (5 minutes).

### Advanced Shell Commands

1. **File Manipulation** (20 minutes)
    - Advanced file searching with `find` and `grep`.
        ```sh
        find /path -name "*.txt"
        grep -r "search_term" /path
        ```
    - File compression and archiving with `tar`, `gzip`, `bzip2`.
        ```sh
        tar -cvf archive.tar /path
        tar -xvf archive.tar
        gzip file.txt
        bzip2 file.txt
        ```

2. **Process Management** (15 minutes)
    - Monitoring and managing processes with `top`, `htop`, `ps`, `kill`.
        ```sh
        top
        ps aux
        kill -9 <pid>
        ```

3. **Networking Commands** (15 minutes)
    - Network troubleshooting with `ping`, `traceroute`, `netstat`.
        ```sh
        ping google.com
        traceroute google.com
        netstat -tuln
        ```

### Bash Scripting

4. **Functions and Loops** (20 minutes)
    - Writing functions in Bash.
        ```sh
        my_function() {
            echo "Hello, $1"
        }
        my_function "World"
        ```
    - Using loops for automation.
        ```sh
        for i in {1..5}; do
            echo "Welcome $i times"
        done
        ```

5. **Conditionals** (10 minutes)
    - Implementing if-else conditions.
        ```sh
        if [ "$1" -gt 0 ]; then
            echo "$1 is positive"
        else
            echo "$1 is non-positive"
        fi
        ```

6. **Input/Output Handling** (10 minutes)
    - Reading user input and handling file I/O.
        ```sh
        read -p "Enter your name: " name
        echo "Hello, $name"
        echo "Some text" > file.txt
        cat file.txt
        ```

### Practical Automation

7. **Automating Common Tasks** (20 minutes)
    - Writing scripts to automate system updates, backups, and log rotation.
        ```sh
        sudo apt-get update && sudo apt-get upgrade -y
        tar -cvf backup.tar /path/to/backup
        logrotate /etc/logrotate.conf
        ```

8. **Scheduling with Cron Jobs** (10 minutes)
    - Creating and managing cron jobs.
        ```sh
        crontab -e
        # Add a job: * * * * * /path/to/script.sh
        crontab -l
        ```

## Hands-On Exercises (1 Hour)

### Exercise 1: Advanced Shell Commands (20 minutes)
- Perform advanced file searches, compress and archive files, and manage processes.

### Exercise 2: Bash Scripting (20 minutes)
- Write a script with functions, loops, and conditionals to automate a task.

### Exercise 3: Practical Automation (20 minutes)
- Create a cron job to schedule the script you wrote in Exercise 2.

### Evening Review
9. **Review and Reflect** (10 minutes)
    - Summarize what you've learned about advanced Linux commands and scripting.
    - Reflect on any challenges faced during hands-on exercises and how to overcome them.
    - Plan for the next day’s topic: Setting Up a Virtual Machine Using VirtualBox or Vagrant.
