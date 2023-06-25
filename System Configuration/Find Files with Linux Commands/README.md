## Lab Objective:

In this lab activity, you’ll navigate a Linux file structure, locate files, and read the contents of files. As a security analyst, it’s key that you know how to navigate, manage, and analyze files remotely via a Linux shell without a graphical user interface.

## Scenario

In this scenario, you have to locate and analyze the information of certain files located in the `/home/analyst` directory.

Here’s how you’ll do this: **First**, you’ll get the information of the current working directory you’re in and display the contents of the directory. **Second**, you’ll navigate to the `reports` directory and list the subdirectories it contains. **Third**, you’ll navigate to the `users` subdirectory and display the contents of the `Q1_added_users.txt` file. **Finally**, you’ll navigate to the `logs` directory and display the first 10 lines of a file it contains.




## Task 1. Get the current directory information

In this task, you must use the commands you learned about to check the current working directory and list its contents.

1. Display your working directory.

2. Display the names of the files and directories in the current working directory.



**Which directory is your current working directory?**


![Capture](https://github.com/cosbey/linux-admin/assets/32424700/d5608bd0-8383-44d8-8d0a-c662e7108c93)
<br>



## Task 2. Change directory and list the subdirectories

In this task, you must navigate to a new directory and determine the subdirectories it contains.

1. Navigate to the `/home/analyst/reports` directory.

2. Display the files and subdirectories in the `/home/analyst/reports` directory.
<br>


**What is the name of the subdirectory in the /home/analyst/reports directory?**

- analyst
- projects
- `users`
- logs





## Task 3. Locate and read the contents of a file

In this task, you must navigate to a subdirectory and read the contents of a file it contains.

1. Navigate to the `/home/analyst/reports/users` directory.

2. List the files in the current directory.

3. Display the contents of the `Q1_added_users.txt` file.



**What department does the employee with the username aezra work in?**
- `Human Resources`
- Finance
- Information Technology
- Sales





**What is the employee_id of the user mreed in the Information Technology department?**
- `1104`
- 1177
- 1188
- 1001



![Capture2](https://github.com/cosbey/linux-admin/assets/32424700/4ac844d3-b7a8-4a98-85d6-e8a6afd536f0)



## Task 4. Navigate to a directory and locate a file

In this task, you must navigate to a new directory, locate a file, and examine the contents of the file.

1. Navigate to the `/home/analyst/logs` directory.

2. Display the name of the file it contains.

3. Display the first **10** lines of this file.

**How many warning messages are in the first 10 lines of the server_logs.txt file?**

![Capture3](https://github.com/cosbey/linux-admin/assets/32424700/996f0b83-fd0c-4567-b675-f0be8dc743dc)

## Observations and Results:

Navigating Linux with the CLI is extremely important and will be beneficial for any analyst. Simply, there are some things you can not do in a quick and productive way with the GUI. With certain commands we can create, edit and delete files with ease. Also, managing user and group permissions within this interface will become critical in future applications. 

## Lessons Learned:

In this lab, we used practical Linux Bash shell commands to:

- navigate directory structures with the `cd` command,
- display the current working directory with the `pwd` command,
- list the contents of a directory with the `ls` command, and
- display the contents of files with the `cat` and `head` commands.

Navigating through directories and reading file contents are fundamental skills that you’ll often use when communicating through the shell.

## Additional Resources
- https://ubuntu.com/download/desktop
- https://www.kali.org/
