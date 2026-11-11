# Linux Permissions and Users
**Date:** 11 November 2026
**Week:** 5, Day 2

## What I understood

Linux has three basic permissions r (read), w (write), x (execute).
Read allows us to view files,write allows us to modify the file contents and execute allows us to run a file as a program/script.

And there are three permission groups such as owner,group and others.
Owner means the user who owns the file.
Group means users belonging to the files assigned group.
Others mean everyone else.

Chmod stands for change mode. It helps us to change the permission of the file.
The numbers like 777,754,644 tell us what permission to give such as r = 4, w = 2, x = 1. So 7 means rwx, 6 means rw-, 5 means r-x and 4 means r– ….etc.

/etc/passwd stores basic user information and /etc/shadow stores password hashes & password related account information.
The shadow is restricted because it contains our password information so to protect it from ordinary users that's why it is restricted.

Chown stands for change owner; it basically changes the ownership of a file or directory.


## What confused me
The /etc/passwd and /etc/shadow confused me a little bit and also in id(user and group identification command) the supplementary group membership confused me.

## Lab output

When I ran cd ~/cybersec-labs after that it navigated to  my cybersec-labs file.

After that I ran echo “test” > permissions-test.txt the echo sends the test to standard output, but > redirects it into the file. So we normally won't see test printed in our terminal.

Then I ran ls -la permissions-test.txt this displays detailed information about that particular file. To list all files, including hidden ones, in the current directory, use ls -la. 

It provided me with this permission string -rw-rw-r–  it basically means it is a regular file and in this the owner and group can read and write. and others can only read.

Then i ran this one by one chmod 777 permissions-test.txt , ls -la permissions-test.txt 
And I got this permission string as -rwxrwxrwx.  It means it is a regular file and the owner,group and others can read,write and execute.

Then i ran this also one by one chmod 644 permissions-test.txt, ls -la permissions-test.txt 
And i got this permission string as  -rw-r–r–. It means it is also a regular file and the owner can read,write and group and others can only read.

Then i ran this also one by one chmod 400 permissions-test.txt , ls -la permissions-test.txt 
And I got this permission string as -r—-----. It means it is also a regular file and the owner can only read it and the group and others have no permissions such as read,write and execute.

Then i ran this also one by one chmod 755 permissions-test.txt , ls -la permissions-test.txt 
And I got this permission string as -rwxr-xr-x. It means it is also a regular file and the owner can read,write and execute while the group and others can only read and execute.


**After the chmod i ran following commands,**

First I ran ls -la /etc/passwd and I got this permission string as  -rw-r–r–. This basically means it is a regular file and the owner can read and write and the group and others can only read it.

Then i ran ls -la /etc/shadow and i got this permission string as -rw-r—--. This means it is a regular file and the owner can read/write and the group can only read it. Others have no permissions.

WHY this matters: “If an attacker reads /etc/shadow they can attempt to crack password hashes offline.” 

After that I ran this ls -la /var/log/auth.log and I got this permission string as -rw-r—--. It means it is also a regular file and the owner can read/write and the group can only read and  others have no permissions.

I saw that in /etc/passwd everyone can read the file while in /etc/shadow only the owner and group can read the file and others have no access to it.

**After that i ran this following commands like,**

*Whoami, id, cat /etc/passwd | tail -5, cat /etc/group | tail -10,* 

When I run whoami it returns my name as lokesh and when I run it it returns my uid(user id), gid(primary group id), then group memberships etc things.

When i run cat /etc/passwd | tail -5 it returns me the last 5 lines and each line has 7 fields and they are separated by colon (:), 

The field 1 showed me username and the field 2 is the password placeholder (the password hash stored separately in /etc/shadow),
The field 3 showed the uid(user id) and the field 4 showed the gid(primary group id),
The field 5 is called the GECOS/comment field(It can contain a user's full name or other descriptive information.) and the field 6 showed the home directory, and finally the field 7 showed the login shell

When i run cat /etc/group | tail -10 it returns the last 10 lines and  i saw each line has 4 fields that separated by colon (:),

Field 1 showed the group name and field 2 showed the group password placeholder (x in typical configurations ),
field 3 showed the gid(group id) and field 4 showed the group members,contains usernames of users belonging to that group. 
It may be empty if no members are explicitly listed. 


**After that i ran the chown commands,**

First i change directory using cd ~/cybersec-labs after i moved to cybersec-labs then i ran touch chown-test.txt it basically created an empty file named as chown-test.txt,
After that I ran ls -la chown-test.txt it displays detailed information about chown-test.txt specifically.

Then i ran sudo chown root chown-test.txt it basically changes the file owner from lokesh to root,
Then again I checked it with this ls -la chown-test.txt and then I saw the change in the file owner.

Then I ran sudo chown lokesh chown-test.txt it changed the file owner back to lokesh,again I checked it using the ls -la chown-test.txt I saw that the file owner is changed and it is the same as the first.


## One thing I can now explain without notes

Permission string contains 10 characters, the first character tells us the file type whether it is a directory or regular file, the next 9 characters tells permissions for owner,group and others, r basically means read, w means write and x means execute.

## What I'll review tomorrow
Tomorrow I will study processes and services —
ps aux, top, kill, systemctl, journalctl.

