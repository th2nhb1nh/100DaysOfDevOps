# Day 2: Advanced Linux Command-Line Operations and Scripting

## Objectives
- Master advanced Linux command-line operations.
- Write advanced shell scripts to automate tasks.
- Learn to manage system resources and processes efficiently.

## Topics Covered
1. Advanced File Manipulation
    - `find` and `grep`
    - `tar`, `gzip`, and `bzip2`
2. Process Management
    - `top`, `htop`, `ps`, and `kill`
3. Networking Commands
    - `ping`, `traceroute`, and `netstat`
4. Functions and Loops in Bash
5. Conditionals in Bash
6. Input/Output Handling in Bash
7. Automating Common Tasks
8. Scheduling with Cron Jobs

## Learning Plan (1-2 Hours)

### Advanced File Manipulation
1. **File Searches with `find` and `grep`** (15 minutes)
    - Perform advanced file searches.
        ```sh
        find /path -name "*.txt"
        grep -r "search_term" /path
        ```
    - **Notes:**
        - 

2. **Compressing and Archiving Files** (10 minutes)
    - Use `tar`, `gzip`, and `bzip2`.
        ```sh
        tar -cvf archive.tar /path
        tar -xvf archive.tar
        gzip file.txt
        bzip2 file.txt
        ```
    - **Notes:**
        - 

### Process Management
3. **Monitoring and Managing Processes** (15 minutes)
    - Use `top`, `htop`, `ps`, and `kill`.
        ```sh
        top
        ps aux
        kill -9 <pid>
        ```
    - **Notes:**
        - 

### Networking Commands
4. **Troubleshooting Network Issues** (10 minutes)
    - Use `ping`, `traceroute`, and `netstat`.
        ```sh
        ping google.com
        traceroute google.com
        netstat -tuln
        ```
    - **Notes:**
        - 

### Functions and Loops in Bash
5. **Writing Functions in Bash** (10 minutes)
    - Create functions.
        ```sh
        my_function() {
            echo "Hello, $1"
        }
        my_function "World"
        ```
    - **Notes:**
        - 

6. **Using Loops for Automation** (10 minutes)
    - Write loops.
        ```sh
        for i in {1..5}; do
            echo "Welcome $i times"
        done
        ```
    - **Notes:**
        - 

### Conditionals in Bash
7. **Implementing If-Else Conditions** (10 minutes)
    - Write if-else conditions.
        ```sh
        if [ "$1" -gt 0 ]; then
            echo "$1 is positive"
        else
            echo "$1 is non-positive"
        fi
        ```
    - **Notes:**
        - 

### Input/Output Handling in Bash
8. **Handling User Input and File I/O** (10 minutes)
    - Read input and handle file I/O.
        ```sh
        read -p "Enter your name: " name
        echo "Hello, $name"
        echo "Some text" > file.txt
        cat file.txt
        ```
    - **Notes:**
        - 

### Automating Common Tasks
9. **Writing Automation Scripts** (10 minutes)
    - Automate system updates, backups, and log rotation.
        ```sh
        sudo apt-get update && sudo apt-get upgrade -y
        tar -cvf backup.tar /path/to/backup
        logrotate /etc/logrotate.conf
        ```
    - **Notes:**
        - 

### Scheduling with Cron Jobs
10. **Creating and Managing Cron Jobs** (10 minutes)
    - Schedule tasks with cron jobs.
        ```sh
        crontab -e
        # Add a job: * * * * * /path/to/script.sh
        crontab -l
        ```
    - **Notes:**
        - 

## Hands-On Exercises (1 Hour)

### Exercise 1: Advanced Shell Commands (20 minutes)
- Perform advanced file searches, compress and archive files, and manage processes.
- **Notes:**
    - 

### Exercise 2: Bash Scripting (20 minutes)
- Write a script with functions, loops, and conditionals to automate a task.
- **Notes:**
    - 

### Exercise 3: Practical Automation (20 minutes)
- Create a cron job to schedule the script you wrote in Exercise 2.
- **Notes:**
    - 

### Evening Review
11. **Review and Reflect** (10 minutes)
    - Summarize what you've learned about advanced Linux commands and scripting.
    - Reflect on any challenges faced during hands-on exercises and how to overcome them.
    - Plan for the next day’s topic: Setting Up a Virtual Machine Using VirtualBox or Vagrant.
    - **Notes:**
        - 
