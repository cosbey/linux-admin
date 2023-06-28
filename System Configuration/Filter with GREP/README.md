# Filter with GREP Command

## Lab Objective:

In this lab, you need to obtain information contained in server log and user data files. You also need to find files with specific names.




## Lab Purpose:

Here’s how you’ll do this: **First**, you’ll navigate to the `logs` directory and return the error messages in the `server_logs.txt` file. **Next**, you’ll navigate to the `users` directory and search for files that contain a specific string in their names. **Finally**, you’ll search for information contained in user files.

With that in mind, you’re ready to practice what you've learned.

## Lab Tool:
- Any Linux distribution



## Task 1. Search for error messages in a log file

In this task, you must navigate to the `/home/analyst/logs` directory and report on the error messages in the `server_logs.txt` file. You’ll do this by using `grep` to search the file and output only the entries that are for errors.

1. Navigate to the `/home/analyst/logs` directory.

2. Use `grep` to filter the `server_logs.txt` file, and return all lines containing the text string `error`.


How many error lines are there in the server_logs.txt file?

- `Six`
- Two
- Eight
- Three

![Capture](https://github.com/cosbey/linux-admin/assets/32424700/871fa0a7-f843-4bad-9904-a5d81343cbae)


## Task 2. Find files containing specific strings

In this task, you must navigate to the `/home/analyst/reports/users` directory and use the correct Linux commands and arguments to search for user data files that contain a specific string in their names.

1. Navigate to the `/home/analyst/reports/users` directory.

2. Using the pipe character (`|`), pipe the output of the `ls` command to the `grep` command to list only the files containing the string `Q1` in their names.

How many files in the /home/analyst/reports/users subdirectory contain “Q1” in their names?

- One
-  `Three`
- Five
- Two


_**Note:** Piping sends the standard output of one command to the standard input of another command for further processing. In the example, the output of the `grep` command is piped to the `ls` command and the output displayed in the shell._

3. List the files that contain the word `access` in their names.

How many files in the /home/analyst/reports/users directory contain “access” in their names?

- Five
- `Four`
- None
- Three

![Capture2](https://github.com/cosbey/linux-admin/assets/32424700/cb55685d-ca46-4250-a6b1-3ea04d490197)


## Task 3. Search more file contents

In this task, you must search for information contained in user files and report on users that were added and deleted from the system.

1. Display the files in the the `/home/analyst/reports/users` directory.

2. Search the `Q2_deleted_users.txt` file for the username `jhill`.

Did you find the username `jhill` in the Q2_deleted_users.txt file?

- `Yes`
- No



3. Search the `Q4_added_users.txt` file to list the users who were added to the `Human Resources` department.

_**Note:** In order for `grep` to interpret a string of two or more words correctly, you must enclose it in quotes (`"Human Resources"`)._

How many users were added to the Human Resources department in quarter 4?

- Three
- Five
- One
-  `Two`


![Capture4](https://github.com/cosbey/linux-admin/assets/32424700/aac1e870-7589-4b0d-af6b-3bbced118dc1)



## Lessons Learned: 


We have used the command line and `grep` to:

- search for specific information contained in files, and
- find files containing specific strings that were piped into `grep`.


