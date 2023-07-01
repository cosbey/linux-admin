# Project: Linux OS Hardening - File Permissions

## Project description

In this project, I performed some simple CLI commands to configure authorization for directories and files.

Authorization is the concept of granting access to specific resources in a system. It's important because without authorization any user could access and modify all files belonging to other users or system files. This would certainly be a security risk.

In Linux, file and directory permissions are used to specify who has access to specific files and directories. In this case, I explored file and directory permissions to change the ownership to limit who can access them.

As a security analyst, setting appropriate access permissions is critical to protecting sensitive information and maintaining the overall security of a system.

## Scenario

The goal of a security analyst is to harden the security and environment whether it's a network or an operating system. In this scenario, the analyst must examine and manage the permissions on the files in the `/home/researcher2/projects` directory for the `researcher2` user.

The `researcher2` user is part of the `research_team` group.

The security analyst must also check the permissions for all files in the directory, including any hidden files, to make sure that permissions align with the authorization that should be given. When it doesn't, you must change the permissions.


The steps and following tasks are:

1. **First**, check the user and group permissions for all files in the `projects` directory. 
2. **Next**, check whether any files have incorrect permissions and change the permissions as needed. 
3. **Finally**, the analyst must check the permissions of the `/home/researcher2/projects/drafts` directory and modify these permissions to remove any unauthorized access.


## Check file and directory details


The first step is to explore the permissions of the `projects` directory and list the files it contains. The project starts with `/home/researcher2` as the current working directory. This is because I am changing permissions for files and directories specifically belonging to the `researcher2` user.

1. Navigate to the `projects` directory.

2. List the contents and permissions of the `projects` directory.

The permissions of the files in the `projects` directory are as follows:

![Pasted image 20230629225744](https://github.com/cosbey/linux-admin/assets/32424700/578de4d4-74a1-4e5e-822b-e0dd1d95969a)

**Note:** _The date and time information returned is the same as the date and time when you ran the command. Therefore, it is different from the date and time in the example._


## Describe the permissions string

The permissions string is a 10-character string begins each entry and indicates how the permissions on the file are set. For instance, a directory with full permissions for all owner types would be `drwxrwxrwx`:

- The 1st character indicates the file type. The `d` indicates it’s a directory. When this character is a hyphen (`-`), it's a regular file.
- The 2nd-4th characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the user. When one of these characters is a hyphen (`-`) instead, it indicates that this permission is not granted to the user.
- The 5th-7th characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the group. When one of these characters is a hyphen (`-`) instead, it indicates that this permission is not granted for the group.
- The 8th-10th characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the owner type of other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (`-`) instead, that indicates that this permission is not granted for other.

The second block of text in the expanded directory listing is the user who owns the file. The third block of text is the group owner of the file.

Before I explore how to change file permissions, I would like to give a brief description on how to conduct the modification. Essentially, there are two ways an administrator can change the permission of a file or directory through the `chmod` command. 

1. After identifying the permissions string, administrators can change each character for all owner types. The `chmod` command requires two arguments. The first argument indicates how to change permissions, and the second argument indicates the file or directory that you want to change permissions for.  For example, the following command would add all permissions to *login_sessions.txt*:

`chmod u+rwx,g+rwx,o+rwx login_sessions.txt`

*If you wanted to take all the permissions away, you could use*

`chmod u-rwx,g-rwx,o-rwx login_sessions.txt`

2. The `chmod` command using octal notation also allows you to specify permissions. Octal notation represents each permission as a three-digit number.

The three digits in octal notation correspond to three sets of permissions: owner, group, and others. Each digit represents a combination of three binary bits, where 1 indicates the permission is granted and 0 indicates it is not granted.

The first digit represents the owner's permissions, the second digit represents the group's permissions, and the third digit represents the permissions for others. The permissions are represented as follows:

- 4: Read permission
- 2: Write permission
- 1: Execute permission

For example, if you want to give the owner read and write permissions, and the group and others read-only permissions, you would use the octal number 644. The command to do this would be `chmod 644 filename`.

Here are a few examples of octal notation and their corresponding permissions:

`chmod 777 filename`
*Gives full read, write, and execute permissions to the owner, group, and others.*

`chmod 750 filename`
*Gives read, write, and execute permissions to the owner, read and execute permissions to the group, and no permissions to others.*

For this project, I performed the following tasks using the octal notation.




## Change file permissions

In this task, the analyst must determine whether any files have incorrect permissions and then change the permissions as needed. This action will remove unauthorized access and strengthen security on the system. The organization does not allow `other` to have write access to any files. Based on the permissions established, identify which file needs to have its permissions modified. Use a Linux command to modify these permissions.

None of the files should allow the `other` users to write to files.

1. Check whether any files in the `projects` directory have write permissions for the owner type of other.

**Which file grants other users write permissions?**

- project_m.txt
- project_t.txt
- `project_k.txt`


![Pasted image 20230629231353](https://github.com/cosbey/linux-admin/assets/32424700/27e17d5e-f8c0-4559-bd3b-2eb1d7fc31f2)


2. Change the permissions of the file identified in the previous step so that the owner type of other doesn’t have write permissions.

![Pasted image 20230629231539](https://github.com/cosbey/linux-admin/assets/32424700/cc50bf7e-d2a2-442c-9761-e3037b5332c4)



**Note:** _Permissions are granted for three different types of owners, namely user, group, and other._

_In the `chmod` command `u` sets the permissions for the user who owns the file,`g` sets the permissions for the group that owns the file, and `o` sets the permissions for others._

3. The file `project_m.txt` is a restricted file and should not be readable or writable, even by the group. List the contents and permissions of the current directory and check if the group has read or write permissions.

**What are the group permissions on the project_m.txt file?**

- Read and write
- `Read only`
- Read, write and execute

4. Use the `chmod` command to change permissions of the `project_m.txt` file so that the group doesn’t have read or write permissions.

![Pasted image 20230629231754](https://github.com/cosbey/linux-admin/assets/32424700/3ce8d979-2809-47ab-847f-b44a73138277)


## Change file permissions on a hidden file


In this task, the analyst must determine if a hidden file has incorrect permissions and then change the permissions as needed. This action will further remove unauthorized access and strengthen security on the system. 

The file `.project_x.txt` is a hidden file that has been archived and should not be written to by anyone. (The user and group should still be able to read this file.)

1. Check the permissions of the hidden file `.project_x.txt` and answer the question that follows.

**Which owner type has the incorrect write permissions?**
- `The user and the group`
- Just the group
- Just the user


2. Change the permissions of the file `.project_x.txt` so that both the user and the group can read, but not write to, the file.

![Pasted image 20230629232022](https://github.com/cosbey/linux-admin/assets/32424700/44b53a96-6379-4244-9de7-ff7598f26fa9)

## Change directory permissions

The goal in this task is to change the permissions of a directory to further establish privilege rights `researcher2`. First, you’ll check the group permissions of the `/home/researcher2/projects/drafts` directory and then modify the permissions as required. (You should be in the `projects` directory for this task.)

Only the `researcher2` user should be allowed to access the `drafts` directory and its contents. (This means that only `researcher2` should have execute privileges.)

1. Check the permissions of the `drafts` directory and answer the following question.

**Does the group have access to the drafts directory?**

- No
- `Yes`



2. Remove the execute permission for the group from the `drafts` directory.

![Pasted image 20230629232231](https://github.com/cosbey/linux-admin/assets/32424700/2a3802c4-436e-4237-9dc3-57a4df6e3060)

## Summary

Understanding how to navigate and manage permissions via CLI is critical as a security analyst. Identifying proper privileges' for users and groups is a key principle for OS hardening. From a defense in depth perspective, monitoring and managing access adds and additional layer for security. It limits a threat actor's potential ability to traverse the network and file system if a vulnerability is exploited. A security analyst's position is to not only identify a potential issue, but to rectify it right away. Offering the proper access rights to users and groups in a network is only another way of preventing an incident from escalating.

In this project, I was able to practice typical Linux command line techniques to manage file permissions from the shell. The following tasks were performed:

- Examine file and directory permissions.
- Identify hidden files and directories.
- Evaluate user and group permissions explicitly.
- Change permissions on files and directories.
