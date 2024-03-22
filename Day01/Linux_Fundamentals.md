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

