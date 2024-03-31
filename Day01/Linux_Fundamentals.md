####  Learning Linux 

<details>
<summary>Linux Essential Commands</summary>
<ul>
<li>Linux remote text-mode login:
<p>For Remote text mode login uses use the SSH means Secure Shell untile the ssh telnet is used for remote connection , Telenet was highly insecure as it did not encrypt communication between you and the server you were connecting to. This meant that anyone on the same network with you can steal your linux user password and see everyting you did on that server during your telnet session. The SSh protocol uses strong encryption to avoid this and the OpenSSH Daemon is build very carefully to avoid security bugs as much as possible. </p>
</li>
<li> Linux Commands:
<p>

- command use a log listing format 

```
ls -l 
```
- TAB: Suggest and Autocomplete , so for example if print command ls /u and hit tab one time it automatically complete the /usr/ and hit 2 times tab it show you available directories.

- if you do not know the which command is use to make file use apropos create file it give you releate command to make file 

```
apropos create file 
```
- to list all hidden file and directories use 
`````
ls -a
`````

- Linux file system tree 
![](https://miro.medium.com/v2/resize:fit:720/format:webp/0*bFnHaO8eYpW3dSuz)

</p>
</li>

</ul>
</details>

#### Hard Links 
- Every file on the Linux filesystem starts with a single hard link. The link is between the filename and the actual data stored on the filesystem.

- Why we need multiple hard links?

#### Soft Links 
- Symbolic links (also called "soft" links) are files that point to a file or directory in your system, but don't mirror the other file's data.


#### List , set , and change standard file permission

-  ```` chgrp ````  command  use to change the group name / directory name.

- ``` chown ```  command is use to change the owner.

#### SUID, SGID, And Sticky Bit
- SUID, short for Set User ID, is a special permission that can be assigned to executable files. When an executable file has the SUID permission enabled, it allows users who execute the file to temporarily assume the privileges of the file's owner

- SGID, which stands for Set Group ID, is another special permission that can be applied to executable files and directories. When an executable file has the SGID permission enabled, it allows users who execute the file to temporarily assume the group ownership of the file.

- The "sticky bit" is a directory-level special permission that restricts file deletion, meaning only the file owner can remove a file within the directory.


#### Search For Files 

 - ``` find /usr/share/ -name '*.jpg ```  The find command in Linux is a dynamic utility designed for comprehensive file and directory searches within a hierarchical structure

 - ``` find /lib64/ -size +10M ``` you upload the application and you want to know to what file change in the last time.

-  ``` find -perm 664 ``` find files with exactly 664 permissions.

- ``` sed 's/canda/canada/g' userinfo.txt ``` this command is use to search and replace text in a file in linux.


- ``` cut -d ' ' -f 1 username.txt ``` cut command give what exactly we want to the file it will print the content. In this situation it only return the firt row of the content.

- ``` uniq contries.txt ``` this command only return not repeated words in the file it will not print the duplicate words.


- ``` diff -c file1 file2 ``` this command comapres  the files.

- Pager is a computer program used to view (but not modify) the contents of a text file moving down the file one line or one screen at a time

#### Search file using Grep 

- ``` grep -i 'centos' /etc/os-release ``` Grep allows users to search files for a specific pattern or word and see which lines contain it.

- ``` grep -r 'Centos' /etc/ ``` This commad search the all files in the given directory.

#### Compression And Decompression 
- ``` gzip file1 ``` command is use to compress the file .

- For unzip the file use ``` gunzip  file.gz ``` command.

-  ``` rsynce -a [local directory] username:[remote directory] ``` so this command is use to syncing two directories.

#### Use Input-Output Redirection

- output redirection simply add  greater than sign > in the end of the file and give it to the file where you want to add your output. ex: ```  sort file.txt > sortedfile.txt ``` this is called the output redirections .

#### Working with SSL certificates

- SSL stands for "secure socket layer" And Nowadays ssl is actually TLS: stand for "transport layer security".

- What is SSL Certificates?

#### Operations Deployment

- ``` systemctl reboot ``` command is to use reboot the system. Also if this command not work use ``` sudo systemctl reboot --force ``` and to poweoff replace with reboot.


#### Using Scripting To Automate Task

#### Manage  the startup process and services

-  To see the service file run command ``` systemctl cat sshd.service ``` and to edit the system file use commad ``` sudo systemctl edit --full sshd.service ``` .

#### Diagnose and manage processes
- ``` ps aux ``` command is use to show the current session runing process in the current terminal.

- Signals:- are the interrupts that are sent to the program to specify that an important event has occurred. Events can vary from user requests to invalid memory access errors.

- ``` sudo kill -SIGHUP <PID> ``` command to kill the running process.

- ``` jobs  ``` command to see the background running process.

#### Locate and analyze system log files 

- Everything important that happens on a linux system is saved as a text message somewhere in that are called logs. The linux kernal and most programs that run on it generate status messages ,eroor messages , warning and so on.

- The job of logging daemons is to collect diffrent programs thea generate all these messages all the time is organize them nicely into file and store into logs. The applications that collect and organize and store logs is Rsyslog. Its name comes from a rocket-fast system for logs processing. Rsyslog stores, all logs in the /var/log/directory.

- To check the current boot logs use the command is ``` journalctl -b 0  ```  for previous boot use -1 instead using 0 .

- ``` lastlog ```  This command shows you each user on the system logged in the last time for remote logins. And to see a history  of who logged in  into the system, you can use the ``` last ``` command.


#### Shedule tasks to run ar a set  date and time

##### Scheduling Jobs With cron

- To edit the crontab ues command ``` crontab -e ``` and to list the ``` crontab -l ``` .

- To add the user in the crontab use command ``` sudo crontab -e -u jane ```  , and to remove the user crontab entirely, use the -r to remove the cron table of a diffrent user ``` sudo crontab -r -u <username> ```.

- To set up cron jobs through the use of special directories. The directory for daily tasks, /etc/cron.daily/ , hourly = /etc/cron.hourly/ and similar to monthly and weekly.


##### Scheduling Jobs With anacron

- anacron command is used to execute commands periodically with a frequency specified in days. Its main advantage over cron is that it can be used on a machine which is not running continuously. In cron if a machine is not running on time of a scheduled job then it will skip it, but anacron is a bit different as it first checks for timestamp of the job then decides whether to run it or not and if its timestamp is >=n(n is defined number of days) then runs it after a specified time delay.


##### Scheduling Jobs With at

- The 'at' command fits into the Linux scheduling system as a tool for scheduling tasks to run at a specific time. It's a one-time scheduler, meaning it's designed to schedule tasks that will only run once, unlike the 'cron' command, which is designed for recurring tasks.

-  example:   ``` at 15:00 ```


#### Manage Software with the package manager 

- APT. Advanced Package Tool, more commonly known as APT, is a package management system for Debian, Ubuntu, and other similar Linux distributions. ``` Example: sudo apt install nginx ``` . 


##### Verify Key Resources and Processes 

- To check how much disk space is availble use the command ``` df or df -h ```  to see specific directory space is suing use the command ``` du -sh <directory path> ```.

- To see how much cpu use by the system use command `` uptime `` to see the specific use of the cpu use command ``` lscpu ``` and to see other hardware on the system use command ``` lspci ``` .

- Use `` free  `` command to check the RAM.

- To check the error of the filesystem use the commad ``` sudo xfs_repair <file-path> ``` .


#### Change kernal runtime parameters, persistent and non-persistent

##### Kernal Runtime Parameters

- To see all Kernal runtime parameters currently in usem we can use  the ``` sysctl -a ``` command.

- In this topic i learn how we can do the process non-persistant to persistant so if the kernal stop the process will continue running not stop.

#### SELinux 

- SELinux allow for very fine grained control if what action should be allowed or denied.

- ``` id -Z ``` The id command in Linux is used mainly to identify the UID (User ID) and GID (Group ID) of a user account, including the groups a user belongs to.

- To enable any kernal process use command ``` sysctl -w <process >```.


##### Create and enforce MAC using SELinux

-  Commands to install the SELinux in ubuntu because ubuntu do not have  selinux it have default apparmor so we have to remove aparmor first and intall selinux :- commands are 

```

-  sudo systemctl stop apparmor.service

-  sudo systemctl disable  apparmor.service

-  sudo apt install selinux-basics auditd

- sestatus = to check the status the selinux 

- to enable it run  [sudo selinux-activate]

- sudo systemctl reboot (after reboot the system selinux enable) 

```

- So If the selinux is running on the permissive mode it is not enforcing security rules. its just observing every action on our system passively. So not deny and allow these potential security  violations in the audit log. So we have to install the Audit Daemon earlier. 





