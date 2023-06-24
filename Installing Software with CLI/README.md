# Installing Software with Command Line Interface

## **Lab Objective:** 

In this lab activity, you’ll use the Advanced Package Tool (APT) and `sudo` to install and uninstall applications in a Linux Bash shell.

While installing Linux applications can be a complex task, the APT package manager manages most of this complexity for you and allows you to quickly and reliably manage the applications in a Linux environment.

You'll use **Suricata** and **tcpdump** as an example. These are network security applications that can be used to capture and analyze network traffic.

The virtual machine you access in this lab has a Debian-based distribution of Linux running, and that works with the APT package manager. Using a virtual machine prevents damage to a system in the event its tools are used improperly. It also gives you the ability to revert to a previous state.


## Lab Purpose:


The purpose of this lab is to install, uninstall, and reinstall these applications on your Linux Bash shell. You also need to confirm that you’ve installed them correctly.

Here’s how you'll do this: **First**, you’ll confirm that APT is installed on your Linux Bash shell. **Next**, you’ll use APT to install the Suricata application and confirm that it is installed. **Then**, you’ll uninstall the Suricata application and confirm this as well. **Next**, you’ll install the tcpdump application and list the applications currently installed. **Finally**, you’ll reinstall the Suricata application and confirm that both applications are installed.

## Lab Tool: Debian-based Linux Distribution



## Task 1. Ensure that APT is installed

First, you’ll check that the APT application is installed so that you can use it to manage applications. The simplest way to do this is to run the apt command in the Bash shell and check the response.

The Bash shell is the command-line interpreter currently open on the left side of the screen. You’ll use the Bash shell by typing commands after the prompt. The prompt is represented by a dollar sign ($) followed by the input cursor.

- Confirm that the APT package manager is installed in your Linux environment. To do this, type `apt` after the command-line prompt and press **ENTER**.

When installed, `apt` displays basic usage information when you run it. This includes the version information and a description of the tool:


![Capture](https://github.com/cosbey/linux-admin/assets/32424700/9d787382-3632-4354-85c3-34905eb0e94a)



APT is already installed by default in the Linux Bash shell in this lab because this is a Debian-based system. APT is also the recommended package manager for Debian. If you’re using another distribution, a different package manager, such as YUM, may be available instead.


## Task 2. Install and uninstall the Suricata application

In this task, you must install Suricata, a network analysis tool used for intrusion detection, and verify that it installed correctly. Then, you’ll uninstall the application.

1. Use the APT package manager to install the Suricata application.

Type `sudo apt install suricata` after the command-line prompt and press **ENTER**.

_**Note:** The `apt install` and `apt remove` commands must be prefixed with the `sudo` command as elevated privileges are required to install and uninstall software in Linux._

_The Suricata application can take a few minutes to install._

When you install an application with APT, the output displays details of all the software to be installed. This may include additional applications that depend on the new software. These additional applications are called the dependencies of the software to be installed.

When prompted to continue, press the **ENTER** key to respond with the default response. (In this case, the default response is **Yes**.)

2. Verify that Suricata is installed by running the newly installed application.

Type `suricata` after the command-line prompt and press **ENTER**.

When Suricata is installed, version and usage information is listed:

![Capture1](https://github.com/cosbey/linux-admin/assets/32424700/07cfa638-4d20-46d6-a5dc-ed1e585c5bca)



3. Use the APT package manager to uninstall Suricata.

Type `sudo apt remove suricata` after the command-line prompt and press **ENTER**. Press **ENTER** (**Yes**) when prompted to continue.

When prompted to continue, press the **ENTER** key to respond with the default response. (In this case, the default response is **Yes**.)

4. Verify that Suricata has been uninstalled by running the application command again.

Type `suricata` after the command-line prompt and press **ENTER**.

If you have uninstalled Suricata, the output is an error message:

-bash: /usr/bin/suricata: No such file or directory

This message indicates that Suricata can't be found anymore.

![Capture4](https://github.com/cosbey/linux-admin/assets/32424700/5db8d0eb-1a5d-4e72-a9ef-85408f692d54)

## Task 3. Install the tcpdump application

In this task, you must install the tcpdump application. This is a command-line tool that can be used to capture network traffic in a Linux Bash shell.

- Use the APT package manager to install tcpdump.

Type `sudo apt install tcpdump` after the command-line prompt and press **ENTER**.


## Task 4. List the installed applications

Next, you need to confirm that you’ve installed the required applications. It's essential to be able to validate that the correct applications are installed. You may also want to check that the accurate versions are installed.

1. Use the APT package manager to list all installed applications.

Type `apt list --installed` after the command-line prompt and press **ENTER**.

This produces a long list of applications because Linux has a lot of software installed by default.

2. Search through the list to find the tcpdump application you installed.

The Suricata application is not listed because you installed and then uninstalled that application:

![Capture6](https://github.com/cosbey/linux-admin/assets/32424700/2d0dc135-411c-4cc0-b74a-6aac1eb9fb38)


## Task 5. Reinstall the Suricata application

In this task, you must reinstall the Suricata application and verify that it has installed correctly.

1. Run the command to install the Suricata application.

Type `sudo apt install suricata` after the command-line prompt and press **ENTER**.

When prompted to continue, press the **ENTER** key to respond with the default response. (In this case, the default response is **Yes**.)

2. Use the APT package manager to list the installed applications.

Type `apt list --installed` after the command-line prompt and press **ENTER**.

3. Search through the list to confirm that the Suricata application has been installed.

![Capture7](https://github.com/cosbey/linux-admin/assets/32424700/a98c9697-868e-4974-b796-6cb586793a45)

## Observations and Results: 
Tools are important; learning how to use the command line effectively will benefit any administrator. Understanding the difference between the Linux distros is vital when learning the command line. Specifically, knowledge that some distros differ when installing applications. For example, Red Hat and Debian use two different package manager commands, YUM and APT, respectively. These are the basics that assist in developing critical skills for commanding this environment and remediating issues.
## Lessons Learned: 
In this lab, I learned the following:
- How to verify APT package manager is installed on Debian-based Linux
- Install and uninstall applications via CLI
- How to list installed applications

**Additional Resources:** 
- https://ubuntu.com/download/desktop
- https://www.kali.org/

