
## Lab Objective:

Another important concept in security is authentication. *Authentication is the process of a user proving that they are who they say they are in the system.*

When managing this, security analysts need to ensure:

- not all users get access to the system,
- new users (those who are new to the organization or a group) are added to the system, and
- current users who change groups or leave the organization are deleted from the system.

The objective of this lab is to use the `useradd`, `usermod`, `userdel`, and `chown` commands to manage user access in the Linux Bash shell.

>**Important:** You must use `sudo` at the beginning of all the commands you use in this lab. Adding or removing users and groups are tasks that require root (super user) privileges, and you’ll need to use `sudo` with the commands that are used to perform these tasks.

## Lab Purpose:


The purpose of this lab is to add a new employee with the username - `researcher9` - that have recently joined our organization. We'll add them to the system and continue to manage their access during their time with the organization.

Here’s how we'll complete this task: **First**, we’ll add a new employee to the system and then to their primary group. **Second**, we’ll make this employee the owner of a file related to a particular project. **Third**, we’ll add the new employee to a supplementary group. **Finally**, we’ll delete the employee from the system.





## Task 1. Add a new user

A new employee has joined the Research department. In this task, you must add them to the system. The username assigned to them is `researcher9`.

1. Write a command to add a user called `researcher9` to the system.

The command to complete this step:

`sudo useradd researcher9`



**Next**, you need to add the new user to the `research_team` group.

2. Use the `usermod` command and `-g` option to add `researcher9` to the `research_team` group as their primary group.

The command to complete this step:

`sudo usermod -g research_team researcher9`



## Task 2. Assign file
![Pasted image 20230702113424](https://github.com/cosbey/linux-admin/assets/32424700/57f831f9-caf2-42eb-a9d9-96075e7018f7)

## Task 2. Assign file ownership

The new employee, `researcher9`, will take responsibility for `project_r`. In this task, you must make them the owner of the `project_r.txt` file.

The `project_r.txt` file is located in the `/home/researcher2/projects` directory, and owned by the `researcher2` user.

- Use the `chown` command to make `researcher9` the owner of `/home/researcher2/projects/project_r.txt`.

The command to complete this step:

`sudo chown researcher9 /home/researcher2/projects/project_r.txt`

![Pasted image 20230702114255](https://github.com/cosbey/linux-admin/assets/32424700/2910a93d-4ed4-414f-aefe-f14e4aed86cd)

## Task 3. Add the user to a secondary group

A couple of months later, this employee's role at the organization has changed, and they are working in both the Research and the Sales departments.

In this task, you must add `researcher9` to a secondary group (`sales_team`). Their primary group is still `research_team`.

- Use the `usermod` command with the `-a` and `-G` options to add `researcher9` to the `sales_team` group as a secondary group.

The command to complete this step:

`sudo usermod -a -G sales_team researcher9`


_**Note:** Options for Linux commands are case-sensitive, so make sure you use a lowercase `-a` and an uppercase `-G`._


Add the user to a secondary group

![Pasted image 20230702114528](https://github.com/cosbey/linux-admin/assets/32424700/a70661b1-ade1-4b51-997a-08f071da2926)

## Task 4. Delete a user

A year later, `researcher9`, decided to leave the company. In this task, you must remove them from the system.

1. Run a command to delete `researcher9` from the system:

`sudo userdel researcher9`


This command will output the following message:

Userdel: Group researcher9 not removed because it is not the primary group of user researcher9.  

This is expected.

_**Note:** When you create a new user in Linux, a group with the same name as the user is automatically created and the user is the only member of that group. After removing users, it is good practice to clean up any such empty groups that may remain behind._

2. Run the following command to delete the `researcher9` group that is no longer required:

`sudo groupdel researcher9`

Delete a user

![Pasted image 20230702115605](https://github.com/cosbey/linux-admin/assets/32424700/e8fc4875-d1c1-4735-961a-594e42e5f3d2)


## Observations and Results:
From an administrator's standpoint, managing users and groups in the Linux environment is a fundamental need. Specifically speaking, authentication is paramount for security reasons right next to authorization. However, understanding the use of root privileges and admin rights are extremely important. We know that normal business operations should not be conducted with root access at all. Operating tasks with admin privileges is a risky and should be avoided. Using the sudo command is essential in this case. 

The primary purpose of "sudo" is to improve security by providing a controlled and auditable way to perform administrative tasks. It helps prevent the need for users to have constant root access, which can be risky and potentially lead to unintended system modifications or security breaches. Instead, users are granted specific commands or operations that they can execute with elevated privileges.



## Lessons Learned:



In this lab, we have used basic Linux Bash shell commands to:

- add a new user,
- add a user to a group,
- change user permissions on files, and
- delete a user.





