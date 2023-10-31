
**Lab Objective:**

Learn how to find, examine, and alter configuration files in Snort.

**Lab Purpose:**

With so many text files, manipulating text becomes crucial in managing Linux and its applications. In this chapter, you’ll use several commands and techniques for manipulating text in Linux.

**Lab Tool:**

Command-line interface, Terminal, Kali Linux, Snorthe

**Lab Topology:**

You can use any Bash shell in the Linux environment.

**Lab Walkthrough:**




#### Step one: Use CAT
 First, we used the **cat** command to display the contents of the Snort configuration file.
```
cat /etc/snort/snort.conf
```

![[Pasted image 20231028005159.png]]


As you can figure, this isn't the most convenient way to view the contents of this file. It is extremely large and not practical at all. However, there are other commands we can utilize and can provide more practicality to view a file. 

#### Step two: Finding the head

If you just want to view the beginning of a file, you can use the **head** command. By default, this command displays the first 10 lines of a file. The following command, for instance, shows you the first 10 lines of `snort.conf`:

```
head /etc/snort/snort.conf
```

![[Pasted image 20231028142523.png]]
If you want to see more or fewer than the default 10 lines, enter the quantity you want with the dash (-) switch after the call to **head** and before the filename. For example, if you want to see the first 20 lines of the file, you would enter the command

```
head -20 /etc/snort/snort.conf
```

![[Pasted image 20231028142620.png]]
#### Step three: Finding the tail

The tail command is similar to the **head** command, but it’s used to view the last lines of a file. Let’s use it on `snort.conf`:

```
tail /etc/snort/snort.conf
```


You can display more lines by grabbing the last 20 lines of `snort.conf`. As with the **head** command, you can tell tail how many lines to display by entering a dash (-) and then the number of lines between the command and the filename,

```
tail -20 /etc/snort/snort.conf
```

![[Pasted image 20231028142740.png]]
#### Step four: Numbering the Lines

Sometimes—especially with very long files—we may want the file to display line numbers. Since `snort.conf`  has more than 600 lines, line numbers would be useful here. This makes it easier to reference changes and come back to the same place within the file. To display a file with line numbers, we use the **nl** (number lines) command.  

```
nl /etc/snort/snort.conf
```

![[Pasted image 20231028143137.png]]

Each line now has a number, making referencing much easier. Note that this command skips the numbering for the blank lines.


#### Step five: Filtering Text with grep

The command **grep** is probably the most widely used text manipulation command. It lets you filter the content of a file for display. If, for instance, you want to see all lines that include the word output in your `snort.conf` file, you could use **cat** and ask it to display only those lines:

```
cat /etc/snort/snort.conf | grep output
```

This command will first view `snort.conf` and then use a pipe `(|)` to send it to **grep**, which will take the file as input, look for lines with occurrences of the word output.

![[Pasted image 20231028143625.png]]


#### Step five: Using sed to find and Replace

The **sed** command lets you search for occurrences of a word or a text pattern and then perform some action on it. The name of the command is a contraction of stream editor. In its most basic form, **sed** operates like the Find and Replace function in Windows. Search for the word `mysql` in the `snort.conf` file using **grep**, like so:

```
cat /etc/snort/snort.conf | grep mysql
```

![[Pasted image 20231028143817.png]]

You should see that the **grep** command found two occurrences of `mysql`. Our next step is to replace every occurrence of `mysql` found in the Snort config file. Take a look at the following command:

```
sed s/mysql/MySQL/ snort.conf > snort2.conf
```

This will only replace the first occurrence. However, we can choose to select to replace all occurrences as well. 


```
sed s/mysql/MySQL/g snort.conf > snort2.conf
```


#### Step six: Viewing Files with more and less command

Using cat is a great way to display contents of a text file, but we have other options. Sometimes viewing the contents can be extremely difficult especially when the file is very large. The **more** and **less** commands will come in handy in these terms. 

```
more /etc/snort/snort.conf
```

The **more** command displays a page of a file at a time using the enter key.

![[Pasted image 20231031023652.png]]


#### Step seven: Displaying and filtering with less

The less command is similar to more, but with additional functionality.  With **less**, we have the ability to not only scroll through a file but filter it for specific terms. 

```
less /etc/snort/snort.conf
```

![[Pasted image 20231031024300.png]]
Notice in the bottom left of the screen that **less** has highlighted the path to the file. If you press the forward slash `(/)` key, less will let you search for terms in the file. For instance, when you first set up Snort, you need to determine how and where you want to send your intrusion alert output. To find that section of the configuration file, you could simply search for `output`, like so:

![[Pasted image 20231031024216.png]]

This will immediately take you to the first occurrence of output and highlight it. You can then look for the next occurrence of output by typing n (for next).

#### Summary

Linux has numerous ways of manipulating text, and each way comes with its own strengths and weaknesses. We’ve touched on a few of the most useful methods in this chapter, but I suggest you try each one out and develop your own feel and preferences.

