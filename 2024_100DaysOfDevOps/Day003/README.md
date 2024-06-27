# Day 3: Set Up a Virtual Machine Using VirtualBox or Vagrant for Lab Environments

## Objectives
- Understand the use of VirtualBox and Vagrant for creating and managing virtual machines.
- Set up a virtual machine using VirtualBox.
- Use Vagrant to automate the setup of virtual environments.

## Topics Covered
1. Introduction to VirtualBox
2. Setting Up a Virtual Machine with VirtualBox
3. Introduction to Vagrant
4. Creating a Vagrantfile
5. Provisioning a Virtual Machine with Vagrant
6. Managing Vagrant Environments

## Learning Plan (1-2 Hours)

### Introduction to VirtualBox
1. **Overview of VirtualBox** (10 minutes)
    - Learn the basics of VirtualBox and its use cases.
    - **Notes:**
        - 

### Setting Up a Virtual Machine with VirtualBox
2. **Installing VirtualBox** (10 minutes)
    - Download and install VirtualBox.
        - Visit [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads) and follow installation instructions.
    - **Notes:**
        - 

3. **Creating a New Virtual Machine** (15 minutes)
    - Set up a new virtual machine in VirtualBox.
        - Choose OS type, allocate memory, and create a virtual hard disk.
        - Install a Linux distribution (e.g., Ubuntu) on the virtual machine.
    - **Notes:**
        - 

### Introduction to Vagrant
4. **Overview of Vagrant** (10 minutes)
    - Learn the basics of Vagrant and its benefits for automating virtual machine setups.
    - **Notes:**
        - 

### Creating a Vagrantfile
5. **Writing a Basic Vagrantfile** (15 minutes)
    - Create a new directory for your Vagrant project.
        ```sh
        mkdir my-vagrant-project
        cd my-vagrant-project
        vagrant init
        ```
    - Edit the generated `Vagrantfile` to configure your virtual machine.
        ```ruby
        Vagrant.configure("2") do |config|
            config.vm.box = "ubuntu/bionic64"
        end
        ```
    - **Notes:**
        - 

### Provisioning a Virtual Machine with Vagrant
6. **Provisioning and Managing the VM** (15 minutes)
    - Start and provision your Vagrant virtual machine.
        ```sh
        vagrant up
        vagrant ssh
        ```
    - **Notes:**
        - 

### Managing Vagrant Environments
7. **Managing Vagrant Machines** (10 minutes)
    - Learn how to manage Vagrant environments with commands like `vagrant halt`, `vagrant destroy`, and `vagrant status`.
        ```sh
        vagrant halt
        vagrant destroy
        vagrant status
        ```
    - **Notes:**
        - 

## Hands-On Exercises (1 Hour)

### Exercise 1: Set Up a VM with VirtualBox (20 minutes)
- Create and configure a virtual machine in VirtualBox.
- **Notes:**
    - 

### Exercise 2: Automate VM Setup with Vagrant (20 minutes)
- Write a `Vagrantfile` and provision a virtual machine using Vagrant.
- **Notes:**
    - 

### Exercise 3: Manage Vagrant Environments (20 minutes)
- Practice managing your Vagrant environment with various Vagrant commands.
- **Notes:**
    - 

### Evening Review
8. **Review and Reflect** (10 minutes)
    - Summarize what you've learned about setting up and managing virtual machines using VirtualBox and Vagrant.
    - Reflect on any challenges faced during hands-on exercises and how to overcome them.
    - Plan for the next day’s topic: Kubernetes (K8s) Introduction and Architecture.
    - **Notes:**
        - 
