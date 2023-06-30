# Managing Files with Linux Commands

## Lab Objective:

In this lab activity I used Linux commands to modify a directory structure and the files it contains.

Also, I utilized the nano text editor to add text to a file.

As a security analyst, creating, removing, and editing directories and files are core tasks you’ll need to perform to help you to manage data. This lab was performed in an virtual environment with installed content. However, reviewing the lab notes can help other administrators learne how to manage files from the CLI and in Linux altogether.


## Lab Purpose:

The purpose is to ensure that the `/home/analyst` directory is properly organized.

You have to make a few changes to the `/home/analyst` directory and the files it contains.

You also have to edit a file to record the changes or updates you make to the directory.

_**Note:** The lab starts with your user account, called `analyst`, already logged in to a Bash shell. This means you can start with the tasks as soon as you click the **Start Lab** button._

When you start, the `/home/analyst` directory contains the following subdirectories and files:

![image](https://github.com/cosbey/linux-admin/assets/32424700/14e5e7e6-8330-4650-a875-a0fcc4880787)



You need to modify the `/home/analyst` directory to the following directory and file structure:

![image](https://github.com/cosbey/linux-admin/assets/32424700/3b8c4415-009b-4b79-89e8-8772a22e657c)


Here’s how you’ll do this: **First**, you’ll create a new subdirectory called logs in the `/home/analyst` directory. **Next**, you’ll remove the `temp` subdirectory. **Then**, you’ll move the `Q3patches.txt` file to the `reports` subdirectory and delete the `tempnotes.txt` file. **Finally**, you’ll create a new `.txt` file called `tasks` in the `notes` subdirectory and add a note to the file describing the tasks you've performed.


## Task 1. Create a new directory

First, you must create a dedicated subdirectory called `logs`, which will be used to store all future log files.

1. Create a new subdirectory called `logs` in the `/home/analyst` directory.

2. List the contents of the `/home/analyst` directory to confirm that you’ve successfully created the new `logs` subdirectory.

The output should list the original three directories and the new `logs` subdirectory:

`logs notes reports temp`



## Task 2. Remove a directory

Next, you must remove the `temp` directory, as you’ll no longer be placing items in it.

1. Remove the `/home/analyst/temp` directory.

2. List the contents of the `/home/analyst` directory to confirm that you have removed the `temp` subdirectory.

The `temp` directory should no longer be listed:

`logs notes reports`



![Pasted image 20230628210151](https://github.com/cosbey/linux-admin/assets/32424700/69105840-28cc-424b-a7bc-6b65e9065116)





## Task 3. Move a file

The `Q3patches.txt` file contains notes taken on third-quarter patches and is now in the correct reporting format.

You must move the  `Q3patches.txt` file from the `notes` directory to the `reports` directory.

1. Navigate to the `/home/analyst/notes` directory.

2. Move the `Q3patches.txt` file from the `/home/analyst/notes` directory to the `/home/analyst/reports` directory.

3. List the contents of the `/home/analyst/reports` directory to confirm that you have moved the file successfully.

When you list the contents of the `reports` directory, it should show that three quarterly report files are now in the `reports` directory:

`Q1patches.txt Q2patches.txt Q3patches.txt` 



## Task 4. Remove a file

Next, you must delete an unused file called `tempnotes.txt` from the `/home/analyst/notes` directory.

1. Remove the `tempnotes.txt` file from the `/home/analyst/notes` directory.

2. List the contents of the `/home/analyst/notes` directory to confirm that you’ve removed the file successfully.

No files should be listed in the `notes` directory.



## Task 5. Create a new file

Now, you must create a file named `tasks.txt` in the `/home/analyst/notes` directory that you’ll use to document completed tasks.

1. Use the `touch` command to create an empty file called `tasks.txt` in the `/home/analyst/notes` directory.

2. List the contents of the `/home/analyst/notes` directory to confirm that you have created a new file.

A file called `tasks.txt` should now exist in the `notes` directory:


![Pasted image 20230628210359](https://github.com/cosbey/linux-admin/assets/32424700/6cba640c-3f2f-4896-ae1f-780037253246)


## Task 6. Edit a file

Finally, you must use the nano text editor to edit the `tasks.txt` file and add a note describing the tasks you’ve completed.

1. Using the nano text editor, open the `tasks.txt` file that is located in the `/home/analyst/notes` directory.

_**Note:** This action changes the shell from the normal Bash interface to the nano text editor interface._

2. Copy and paste the following text into the text input area of the nano editor:

3. Press **CTRL+X** to exit the nano text editor.

This triggers a prompt asking **Save modified bufferer?**

4. Press **Y** to confirm that you want to save the new data to your file. (Answering "no" will **discard** changes.)
    
5. Press **ENTER** to confirm that **File Name to Write** is `tasks.txt`.
    
    _**Note:** The recommended sequence of commands for saving a file with the nano text editor is to use **CTRL+O** to tell nano to save the file and then use **CTRL+X** to exit immediately._
    
    _In this web-based lab environment, the **CTRL+O** command is intercepted by your web browser and is interpreted as a request to save the web page. The sequence used here is a commonly used alternative that achieves the same end result._
    
6. Use the `clear` command to clear the Bash shell window and remove any traces of the nano text input area.
    

_**Note:** Most Bash shells typically handle the screen cleanup after you exit nano. In this lab environment, nano sometimes leaves some text clutter around the edges of the screen that the `clear` command cleans up for you._

7. Display the contents of the `tasks.txt` file to confirm that it contains the updated task details.

This file should now contain the contents of the `tasks.txt` file that you added and saved in previous steps:


![Pasted image 20230628210501](https://github.com/cosbey/linux-admin/assets/32424700/439e3ed0-a47f-424f-9f7b-cbaef972ecf2)


![Pasted image 20230628210736](https://github.com/cosbey/linux-admin/assets/32424700/93a97aaf-ae44-48ea-948e-44fdbb11cca8)

## Observations and Results: 
Learning how to manage files in Linux is of utmost importance for a security analyst. As a security analyst, you'll frequently work with server logs, configuration files, user access reports, and other critical data. Being able to navigate, analyze, and manipulate files efficiently and securely is essential for identifying potential vulnerabilities, investigating security incidents, and implementing necessary security measures. Linux provides powerful command-line tools for file management, allowing you to search, filter, and extract relevant information. Additionally, understanding file permissions, access control, and file integrity verification techniques enables you to ensure the confidentiality, integrity, and availability of sensitive data. Mastering file management in Linux empowers security analysts to effectively perform their duties, enhance system security, and safeguard valuable assets.

## Lessons Learned: 
In this lab, we have used basic Linux Bash shell commands to:

- create and remove directories,
- copy, move, and remove files, and
- edit files with the nano text editor.
