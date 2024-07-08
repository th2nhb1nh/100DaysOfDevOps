# Day 3: Advanced Shell Scripting Techniques

- [Day 3: Advanced Shell Scripting Techniques](#day-3-advanced-shell-scripting-techniques)
  - [Objectives](#objectives)
  - [Topics Covered](#topics-covered)
  - [Learning Plan (1-2 Hours)](#learning-plan-1-2-hours)
    - [Advanced Script Structuring](#advanced-script-structuring)
    - [Handling Command-Line Arguments](#handling-command-line-arguments)
    - [Input/Output Redirection and Piping](#inputoutput-redirection-and-piping)
    - [Error Handling and Debugging](#error-handling-and-debugging)
    - [Script Optimization Techniques](#script-optimization-techniques)
  - [Notes](#notes)

## Objectives
- Master advanced shell scripting techniques.
- Write scripts to handle complex tasks and automation.
- Learn to debug and optimize shell scripts.

## Topics Covered
1. Handling Command-Line Arguments
2. Input/Output Redirection and Piping
3. Error Handling and Debugging
4. Script Optimization Techniques

## Learning Plan (1-2 Hours)

### Advanced Script Structuring
1. **Script Organization and Best Practices** (15 minutes)
    - Learn best practices for organizing and structuring scripts.
    - **Notes:**
        - Use meaningful variable names.
        - Modularize code into functions.
        - Comment your code for clarity.
        - Follow a consistent coding style.

### Handling Command-Line Arguments
2. **Processing Arguments in Scripts** (20 minutes)
    - Use `$1`, `$2`, etc., to access command-line arguments.
        ```sh
        echo "First argument: $1"
        echo "Second argument: $2"
        ```
    - Use `getopts` for more complex argument parsing.
        ```sh
        while getopts "a:b:" opt; do
          case $opt in
            a) echo "Option A: $OPTARG";;
            b) echo "Option B: $OPTARG";;
            \?) echo "Invalid option";;
          esac
        done
        ```
    - **Notes:**
        - Handle optional and required arguments.
        - Provide usage information for the script.

### Input/Output Redirection and Piping
4. **Advanced I/O Redirection and Piping** (20 minutes)
    - Use redirection operators and pipes to manage input and output.
        ```sh
        command > output.txt        # overwrite file with new content
        command >> output.txt       # append new content to file
        command < input.txt         # provide content of file as input for command
        command1 | command2         # send output from cmd 1 to cmd for further processing
        ```
### Error Handling and Debugging
5. **Implementing Error Handling** (15 minutes)
    - Use `set -e`, `set -u`, and `set -o pipefail` for robust error handling.
        ```sh
        set -e              
        set -u              
        set -o pipefail     
        ```
    - Trap errors and handle them gracefully.
        ```sh
        trap 'echo "An error occurred"; exit 1' ERR
        ```
    - **Notes:**
        - Use `trap` to handle script termination and errors.
        - Check return values of commands.

### Script Optimization Techniques
6. **Optimizing Shell Scripts** (20 minutes)
    - Identify and eliminate unnecessary commands.
    - Use built-in commands and avoid external processes where possible.
    - Profile script performance with `time` and `strace`.
        ```sh
        time ./myscript.sh
        strace -c ./myscript.sh
        ```
    - **Notes:**
        - Optimize loops and conditionals.
        - Use efficient data structures and algorithms.

## Notes

