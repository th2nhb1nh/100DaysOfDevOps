# Day 2: Advanced Linux Command-Line Operations and Scripting

- [Day 2: Advanced Linux Command-Line Operations and Scripting](#day-2-advanced-linux-command-line-operations-and-scripting)
  - [Objectives](#objectives)
  - [Topics Covered](#topics-covered)
  - [Learning Plan (1-2 Hours)](#learning-plan-1-2-hours)
    - [Advanced File Manipulation](#advanced-file-manipulation)
    - [Process Management](#process-management)
    - [Networking Commands](#networking-commands)
    - [Functions and Loops in Bash](#functions-and-loops-in-bash)
    - [Conditionals in Bash](#conditionals-in-bash)
    - [Input/Output Handling in Bash](#inputoutput-handling-in-bash)
    - [Automating Common Tasks](#automating-common-tasks)
    - [Scheduling with Cron Jobs](#scheduling-with-cron-jobs)

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
    - File search with `find`.
        ```sh
        find /path -type f -name "*.txt"                # find files
        find /path -type d -name "*.txt"                # find directories
        find /path -type f -size +100M -name "*.txt"    # find files with size
        ```
    - Use `grep`
        ```sh
        grep -r "search_term" /path     # recursive search
        # -i: case-insensitive
        # -n: display line numbers with the matched lines
        # -w: search matching words only
        # -c: count matching lines
        ```
    - Combination with `find`
        ```sh
        # `-exec` execute command on each found file with {} be the placeholder for each found file, one by one -> delete it -> `\` is the end of the `-exec` command
        find /path/to/search -name "*.log" -exec rm {} \;

        # `xargs` execute command on the output of `find`
        find /path/to/search -type f -name "*.txt" | xargs grep "search string"
        ```
    => `xargs` could handle mulple files at once -> better performance -> be careful with special characters in filenames
    => use `-print0` with `find` and `-0` with `xargs` to deal with that:
        ```sh
        find /path/to/search -type f -name "*.txt" -print0 | xargs -0 grep "search string"
        ```
    - **Notes:**
      - `-print0` prints full filename with `null` character, instead of newline as `-print` -> command could interprete filenames with newlines or whitespaces correctly. This option corresponds to `xargs -0` 

2. **Compressing and Archiving Files** (10 minutes)
    - Use `tar`, `gzip`, and `zip`.
        ```sh
        tar -cvf archive.tar /path                  # -c: create new tarball
        tar -xvf archive.tar                        # -x: extract a tarball
        tar -cvzf archive.tar.gz /path/to/files     # -z: create compressed tarball
        tar -xvzf archive.tar.gz                    # extract compressed tarball
        gzip file.txt                               # compress a single file
        gunzip filename.gz                          # decompress a file
        zip archive.zip file1 file2 file3           # create a zip archive
        zip -r archive.zip /path/to/directory       # create a zip archive of a directory
        zip -r archive.zip /path/to/directory       # extract a zip file
        ```

### Process Management
3. **Monitoring and Managing Processes** (15 minutes)
    - Use `top`, `htop`, `ps`, and `kill`.
        ```sh
        top             # real-time process monitoring
        htop            # enhanced `top` command (if installed)
        ps aux          # list all running processes
        kill -9 <pid>   # kill process by pid
        killall <name>  # kill all processes with given name
        pkill <pattern> # kill all processes matching a pattern
        command &       # run command in the background
        fg %job_number  # bring background job to foreground
        bg %job_number  # resume suspended job in the background
        ```

### Networking Commands
4. **Troubleshooting Network Issues** (10 minutes)
    - Use `ping`, `traceroute`, and `netstat`.
        ```sh
        ifconfig                    # list all network interfaces
        ping google.com             # check connectivity to an address
        traceroute google.com       # trace the packets' route to the address
        nslookup google.com         # map ip address with domain and vice versa
        dig google.com              # more flexible dns lookup tool
        mtr host                    # combination of `ping` and `traceroute` for network diagnostics
        netstat -tuln               # show network stats
        telnet host port            # connect to remote host on port
        ```

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
        - Simple structure:
        ```sh
        function_name() {
            commands
        }
        # or
        function function_name {
            commands
        }
        ```

6. **Using Loops for Automation** (10 minutes)
    - `for` loop
        ```sh
        for i in {1..5}; do
            echo "Welcome $i times"
        done
        ```
    - `while` loop
        ```sh
        counter=1
        while [$counter -le 5]
        do
            echo "Counter: $counter"
            ((counter++))
        done
        ```
    - **Notes:**
      - Comparision operators: 
        - `-eq`: is equal to `if [ "$a" -eq "$b" ]`
        - `gt`: is greater than `if [ "$a" -gt "$b" ]`
        - `-ge`: is grater than or equal to `if [ "$a" -ge "$b" ]`
        - `<`: is less than (with double parentheses) `(("$a" < "$b"))`

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

### Input/Output Handling in Bash
8. **Handling User Input and File I/O** (10 minutes)
    - Read input and handle file I/O.
        ```sh
        read -p "Enter your name: " name
        echo "Hello, $name"
        echo "Some text" > file.txt
        cat file.txt
        ```

### Automating Common Tasks
9. **Writing Automation Scripts** (10 minutes)
    - Automate system updates, backups, and log rotation.
        ```sh
        sudo apt-get update && sudo apt-get upgrade -y
        tar -cvf backup.tar /path/to/backup
        logrotate /etc/logrotate.conf
        ```

### Scheduling with Cron Jobs
10. **Creating and Managing Cron Jobs** (10 minutes)
    - Schedule tasks with cron jobs.
        ```sh
        crontab -e
        # Add a job: * * * * * /path/to/script.sh
        crontab -l
        ```
    - **Notes:**
        - Generate the crontab using this web: https://crontab.guru/
