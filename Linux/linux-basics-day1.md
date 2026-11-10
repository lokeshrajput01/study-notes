# Linux Basics — Navigation and File Operations
**Date:** 09 November 2026
**Week:** 5, Day 1

## what i understood:

I learned how to find the current directory using pwd,how to view our files using ls and also how I can view the detailed listing,including the hidden files also using ls -la.

How can I move between directories using cd and how can i go back home using cd ~.

I also learned how to create a directory using mkdir and also how to create a file using touch.

I also learned file copying using cp,moving/renaming the file using mv,deleting a file using rm, and displaying the file content using cat.

I also learned how to display the beginning and end of the file using head and tail and also less to provide us with reading the file page by page.

**Command learned:**
| Command | What it does | 
|---|---|
| pwd | shows the current directory. |
| ls | Lists visible files and directories. |
| ls -l | Displays detailed information about files and directories. | 
| ls -la | shows detailed information including hidden files. |
| cd | this changes/moves between the directories. |
| mkdir | it creates a directory. |
| touch | It creates an empty file if it doesn't exist. If the file already exists, it updates its modification timestamp. | 
| cp | This is used to copy files. |
| mv | it moves a file or renames it. |
| rm | it removes or deletes a file. |
| cat | it displays file content. |
| head |it shows the beginning of a file. |
| tail | it shows the ending of a file. |
| less | it reads files page by page. |



## Lab observations:

**Navigation:**

when i run few commands in linux terminal like,

pwd it shows my current directory as home,

Then I run ls it gives me a list of all my files like download,desktop,public,picture etc.

Then i run ls -la this gave me detailed listing about my files, including hidden one’s also,like in that i saw permissions, number of hard links,owner and group,file size information,last modified and saw files and hidden files like start from .bashrc,.profile etc.

Then I ran cd /var/log. I saw that it moved to the log directory,after that I again ran ls -la. I saw the first total number of filesystem blocks allocated to the listed entries 4756 and then I saw a detailed listing of log directory files including the hidden ones also. In this i saw directory,permissions,number of hard links,owner and group,directory size in bytes,last modification time etc information there.

Then I run cd ~ it basically navigates me to home.

**File operations:**

In this I ran mkdir cybersec-labs. It basically created a directory for me named as cybersec-labs.

Then I ran touch test.txt and it created a test file for me named test.

And I also used mkdir -p day1-files to create a directory name as day1-files,after that i run cd day1-files it basically moves me to day1-files.

After that I ran echo “hello world” > file1.txt basically the echo in it prints the text and then the > redirects that text into a file, it basically creates a file if necessary and it overwrites the existing contents.

After that i run cat file1.txt this displays the content like i written “hello world”

Then I ran cp file1.txt file2.txt it created a copy of file 1 for me as file 2, after that I ran ls -l it showed me file 1 and file 2 it basically showed a detailed listing of files.

Then i run mv file2.txt renamed.txt it rename my file2.txt as renamed.txt

In last i run rm file1.txt it removed the file1.txt and i check by running ls -l it now shows only renamed.txt


**Reading files:**

When i ran head /etc/passwd, it gave me first 10 lines by default and then i saw 7 different fields separated by colon ( : ), each field has its own information like as follows,

field 1 shows username, Field 2 usually contains x, indicating that the password hash is stored separately in /etc/shadow.,

field 3 shows UID(user id), field 4 shows GID(primary group id), 

field 5 shows user description or full name, field 6 shows home directory , field 7 shows login shell.

Then I ran the tail /etc/passwd. It gave me the last 10 lines by default and then I saw a similar structure as a head like 7 fields separated by colon( : ).

Then I ran the less /etc/passwd. It basically allows me to read files page by page. It also has the same structure like 7 fields separated by colons ( : ) and also in that i use spacebar for next page, b for previous page, /root to search for root and n for next search and q for quit/exit.  

## What confused me:

At first I was really confused when I saw a total of 4756. I thought that this is the total number of files but this is the total number of filesystem blocks allocated to the listed entries.

## One thing i can explain without notes:
Pwd basically used to find our current directory.

ls basically lists files and directories while ls -la displays detailed information, including hidden files and directories, and the ls -l displays detailed information about files and directories.

The cd changes between directory while mkdir created a directory.

Cp copies a file and mv moves or renames a file and rm deletes a file.

The /var/log  basically stores system and application log files.

The difference between a file and a directory is that a file stores data such as text,images and documents while a directory organises files and other directories inside it.

The total mean in the output of ls -la, It means the total number of filesystem blocks allocated to the listed entries. It does not mean the number of files. 

## What I'll study tomorrow:
Linux permissions and users — chmod, chown, rwx explained, users and groups, /etc/passwd, /etc/shadow, whoami, id, sudo.


