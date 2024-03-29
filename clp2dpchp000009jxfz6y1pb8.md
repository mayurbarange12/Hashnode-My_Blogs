---
title: "Day 5 - Linux Advanced and Shell Scripting"
datePublished: Fri Nov 17 2023 08:49:14 GMT+0000 (Coordinated Universal Time)
cuid: clp2dpchp000009jxfz6y1pb8
slug: day-5-linux-advanced-and-shell-scripting
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1700202136453/37e434a6-ca74-4bff-9cf2-1cd49cc841c8.png
tags: linux, devops, shell, 90daysofdevops, trainwithshubham

---

# **GREP : (Global Regular Expression Print)**

The grep filter searches a file for a particular pattern of characters and displays all lines that contain that pattern.

* `grep ubuntu /etc/passwd` --&gt; It will search a word/string "ubuntu" in a file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700202527875/7d3820b4-b3c5-4772-a27b-c691da965de1.png align="center")

* `grep -i Ubuntu /etc/passwd` --&gt; It will search a string "Ubuntu" insensitive in a file.
    
    (-i = case insensitive)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700202727287/8afa376d-88eb-4a40-b548-5005fa31ef36.png align="center")

How to use this "**grep**" command in a real-based scenario?

* `mkdir logs`
    
* `cd logs/`
    
* `vim applications.logs`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700203331053/fce81d82-e92c-47b0-becb-b4d5c696d1a8.png align="center")

* **Copy and paste logs from samplelogs.com and save it**.
    
* `grep TRACE application.log`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700203658541/f9af80d4-16db-41b6-8a8c-9b3f3d8837e0.png align="center")

* `grep TRACE application.log > trace_only_for_QA.log`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700203885842/46fc1d79-7fdd-4bc9-afba-44909915fe9a.png align="center")

# **AWK : (Aho, Weinberger and Kernighan)**

AWK is a powerful command-line tool in Linux used for processing and manipulating text and data. It reads text line by line, allowing you to search, extract, modify, and print specific patterns or fields within files.

* `awk '{print $1}' application.log` --&gt; To print the first column of the file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700204317248/0302ecaa-b544-46c9-845a-f2627f73b562.png align="center")

* `awk '{print $1,$2}' application.log` --&gt; To print the first and second columns of the file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700204621967/e137a325-fb77-43e6-9789-773b26a31ae6.png align="center")

* `awk '{print NR,$1,$2,$5}' application.log` --&gt; To print the first, second and fifth columns with the Number of Rows of the file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700204825024/f83fcf20-1996-4d06-ad57-dae4f8de4dcf.png align="center")

# **Head**

It displays the first few lines (by default, the first 10 lines) of a text file on the terminal.

* `awk '{print NR,$1,$2,$5}' application.log | head` --&gt;To print the first 10 Rows(Lines) of the file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700205073096/6ef3af18-05f7-4ed2-a79f-ec15dd46efcc.png align="center")

* `awk '{print NR,$1,$2,$5}' application.log | head -20` --&gt; To print first 20 Rows(Lines) of the file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700205197552/c5b598db-a318-4a12-979f-2014d935fa1f.png align="center")

# **Tail**

StartFragmentIt displays the last few lines (by default, the last 10 lines) of a text file on the terminal.EndFragment

* `awk '{print NR,$1,$2,$5}' application.log | tail` --&gt; To print last 10 Rows(Lines) of the file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700205590959/fd00f311-3094-4ed3-abf6-36a104f16d82.png align="center")

* `awk '{print NR,$1,$2,$5}' application.log | tail -20` --&gt; To print last 20 Rows(Lines) of the file.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700205698892/a4f64616-4b82-4cee-87b4-becd120e17dc.png align="center")

## **Alternate way to perform tasks through AWK command**

* **awk /TRACE/ &lt;FileName.log&gt;  --&gt;** To search "TRACE" keyword from file.  (Grep alternate way to search keyword)
    
* **awk '/INFO/ {print $1,$2,$3,$4}' &lt;FileName.log&gt;  --&gt;** To search and print "INFO" keyword of column 1,2,3 & 4 from file.
    
* **awk 'NR&gt;=20 && NR&lt;=40 && /INFO/ {print NR,$1,$2,$4}' &lt;FileName.log&gt;**
    
    **\--&gt;** To print from Row 20 to Row 40 of Keyword "INFO" with column 1,2 & 4 of the file.
    
* **awk 'NR&gt;=10 && NR&lt;=30 {print NR,$1,$2,$5}' &lt;FileName.log&gt;  --&gt;** To print from Row 10 to Row 30 of the file.
    
* **awk 'NR&gt;=20 && NR&lt;=40 && /INFO/ {print NR,$1,$2,$4}' &lt;FileName.log&gt; &gt; INFO\_For\_QA.log  --&gt;** To print from Row 20 to Row 40 of Keyword "INFO" with column 1,2 & 4 Redirect to INFO\_For\_QA.log File.
    
* **awk '$2&gt;"08:52:00" && $2&lt;"08:54:00" {print $1,$2}' &lt;FileName.log&gt;  --&gt;** To print Time from "08:52:00" to "08:00:54" of column 1 and 2 of the file.
    

# **Find**

Find command used to search and locate the list of files and directories based on conditions you specify for files that match the arguments.

Find can be used in a variety of conditions like you can find files by permissions, users, groups, file type, date, size, and other possible criteria.

* **find ~/ -name &lt;FileName.log&gt;   --&gt;** Find in Home directory named as &lt;FileName.log&gt;
    
* **find ~/ -name application.log    --&gt;** Find in Home directory named as application.log
    
* **find ~/ -name \*.log**  --&gt; Find in Home directory named as **all\_file.log** files.
    
* **find ~/ -user ubuntu --&gt;** Find in Home directory anything that has been created by the **user** - **ubuntu.**
    

## **Scenarios of Find command**

* **cp application.log /home/ubuntu  --&gt;** copy application.log file from **source**: /home/ubuntu/logs  to **destination:** /home/ubuntu
    
* **ls -l application.log**
    
    \-rw-rw-r-- 1 ubuntu ubuntu 22929 Nov 16 07:31 application.log
    
* **sudo chgrp mayur application.log --&gt;** I have change group from **ubuntu** to **mayur** of application.log file
    
* **ls -l application.log**
    
    \-rw-rw-r-- 1 ubuntu mayur 22929 Nov 16 07:31 application.log
    
* **find ~/ -group mayur** --&gt; Find in a Home directory which **group name** as **mayur**.
    
    /home/ubuntu/application.log
    

# **Shell Scripting**

In the simplest terms, a shell script is a file containing a series of commands. The shell reads this file and carries out the commands as though they have been entered directly on the command line. Normally the shell scripts has the file extension "**.sh**".

**To create a shell script, you use a text editor(Types of Text-Editor) :**

* **vi** or **vim** is the command line interface text editor.
    
* **gedit** is the **GUI** text editor.
    

### **There are two types to execute shell script :**

* <mark>./&lt;FileName.sh&gt;</mark>
    
* <mark>bash &lt;FileName.sh&gt;</mark>
    

### **How to run a shell script(echo command)?**

* `mkdir myscript`
    
* `cd myscript/`
    
* `vim script-1.sh`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700207145853/2ca8c4ae-c18d-4af6-a344-8a308e913628.png align="center")

```bash
#!/bin/bash
echo "mayur: Hello Guys!!"
```

* `chmod 700 script-1.sh` --&gt; To assign read, write & execute permission to owner/user.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700207649807/6df8a464-bce2-4b11-b374-0523892d8353.png align="center")

* `./script-1.sh` --&gt; To run/execute shell script.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700207704948/c01fc8e7-b248-48a7-ba43-766eb2d27934.png align="center")

### **How to display the date** **through shell script?**

* `vim script-1.sh`
    

```bash
#!/bin/bash
echo "Today's date is:"
date  
# It will display the date.
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700208269828/331b8649-84e1-4b7a-9d0f-397c5aae111d.png align="center")

### **How to create a Folder through Shell Script?**

* `vim MakeDirectory.sh`
    

```bash
#!/bin/bash
echo "What is the name of your folder?"
read foldername
mkdir $foldername
echo "folder created, please check..."
```

* `chmod 700 MakeDirectory.sh`
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700208832661/86b922a4-8acf-4987-825e-de6654157e6c.png align="center")

### **How to use Variable in Shell Script?**

* `vim variable.sh`
    

```bash
#!/bin/bash
name=mayur
echo "my name is $name"
```

* `bash variable.sh` --&gt; Without taking Permission(Read, Write, Execute) we can directly execute shell script through the "**bash**" command.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700209291363/e402a054-2acc-4e3c-866b-976d156f43d3.png align="center")

### **How to use Arguments in Shell Script?**

* `vim ShowArguments.sh`
    

```bash
#!/bin/bash
echo "first argument $1"  --> first argument will display.(test)
echo "second argument $2" --> second argument will display.(trainwithshubham) 
echo "all arguments $@"   --> @ = all arguments will display.(test trainwithshubham hello dosto)
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700209954459/ee820e8f-919d-4c57-ad6a-1397f534b7c2.png align="center")

### **How to install any tool(docker/nginx) through shell script**

* `vim installer.sh`
    

```bash

#!/bin/bash
echo "installing $1" --> Whatever tool name will input it will install
sudo apt update -y  --> (-y = yes)
sudo apt-get install $1 -y  -->  "$1" variable will take input access.
```

* Installing **Docker** Tool:-
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700210337415/b2728418-9f66-4bd9-94aa-e62a00a090e8.png align="center")

* Installing **Nginx** Tool:-
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1700210436602/0db2f09a-cb30-454d-92e7-82f7625ed1d4.png align="center")