# Linux Investigator's Toolkit — grep and find
**Date:** 18 November 2026
**Week:** 5, Day 4

## What I understood

grep basically searches for text inside files. Like if we want to search “root” word then grep will help us to search only “root”.
If we use grep -i, it basically ignores uppercase and lowercase differences and provides us with the specific word like root,ROOT,Root...etc.
grep -r this search recursively in all files in a directory.
grep -n this shows line numbers with results.
grep -v this shows lines that do not contain the specific word.

find basically locates files and directories by their names,types,locations,time and size.
find /path -name “filename” it finds files by exact name.
find “*.log” this finds all .log files.
find  -type f this finds files only.
find  -type d this finds directories only.
find -mtime -1 this finds the last modified files in 24 hours.
find -size +1m this finds files larger than 1 mb.

## What confused me
When I ran find / -name "passwd" 2>/dev/null  this confused me a little bit, specifically this part  2>/dev/null,
Also when i ran grep -i "failed" /var/log/auth.log and  grep -n "session" /var/log/auth.log | head -10
I got grep: /var/log/auth.log: binary files matches.
The binary files matched output also confused me.


## Lab output

First i open my terminal in ubuntu and ran cd ~/cybersec-labs to move to cybersec-labs,  then i ran pwd to check my current directory and then i ran ls -lh /var/log to list files and folders inside the /var/log directory with human readable sizes.

**grep practice:**

First I ran the  grep "error" /var/log/syslog,

I got a very long output in which I saw “error” is highlighted in red color. So it basically means grep searches for the files in /var/log/syslog  that are containing “error” words in it.

After that i ran grep -i "failed" /var/log/auth.log,
I got grep: /var/log/auth.log: binary files matches.

grep detected data that it treated as binary, so it displayed a binary file matches message instead of showing the matching lines. Using grep -a forces grep to treat the file as text. 

But when i ran grep -ai "failed" /var/log/auth.log | head -10, 

I got lines that are containing “failed” words i saw every line has failed in it like passwd check failed for user and my name ,failed to activate service its name and timed out…..etc etc information.

After that i ran grep -i "error" /var/log/syslog | head -20,

I got the first 20 lines and I saw the lines containing the “error” word. -i ignores uppercase and lowercase and provides output that contains “error” words.
Like ERROR,error,Error..etc

After that i ran grep -r "root" /var/log/, 

I got a very-very long output in that i saw first /var/log/apt/history.log:commandline:
in that i saw long information and i saw “root” is highlighted in red color, 
Then i saw /var/log/apt/history.log:install:
In these I also saw long information and “root” is highlighted in red color.
Then i saw lines that are starting with /var/log/cloud-init.log:,
In these lines I saw “root” highlighted in red in every line.

Below that I saw grep: /var/log/auth.log,boot.log,journal,sssd,private,speech and next to it permission denied or binary file matches.
Below that i saw /var/log/bootstrap.log: lines, 
In these lines I saw chroot in each line with the “root” highlighted only. 
Then I saw /var/log/dmesg.0: lines that also had “root” highlighted.
Again I saw below these lines: /va/log/btmp,installer…..etc-etc next to it permission denied.
Then I saw /var/log/installer/curtin-install.log lines in that i also saw “root” is highlighted.
Then I saw /var/log/installer/block/discover.log two lines that also highlighted “root”.
Then I saw /var/log/installer/ubuntu_bootstrap.log.4274 lines that also had “root” highlighted.
Then I saw /var/log/unattended-upgrades/unattended-upgrades-dpkg.log lines in that i saw chroot with “root” highlighted.
Then I saw /var/log/kern.log: lines that also had “root” highlighted.
Then I saw /var/log/syslog,dpkg.log,cloud-init-output.log,dmesg lines that also had “root” highlighted.

So basically it means this searches the “root” word recursively in all files inside a directory & its subdirectories.

After that i ran grep -n "session" /var/log/auth.log | head -10,
I got grep: /var/log/auth.log: binary files match the same as  grep -i “failed” /var/log/auth.log.

After that i ran grep -v "systemd" /var/log/syslog | head -20,
I got the first 20 lines that do not contain “systemd” in it.

**find practice:**

First I ran find /var/log -name "*.log",
It provide me all .log files like term.log,history.log,cloud-init.log….etc
It basically finds all .log files from/var/log directory.

Then I ran find /var/log -type f and also ran find /var/log -type d,
The -type f returned me all files only like /var/log/apt/term.log,eipp.log.xz,cloud-init….etc-etc and the -type d returned me all directories only like /var/log,/var/log/apt,/var/log/chrony….etc-etc.

Then I ran find /var/log -name "*.log" -mtime -1 
This returned me all .log files that were modified in the last 24 hours.
I got this, find: ‘/var/log/chrony’: permission denied,/var/log/auth.log,/var/log/boot.log….etc-etc

Then I also ran find /home -type d,
That returned me all home directories that are present in home like /home,/home/lokesh,/home/lokesh/pictures,screenshots……many more.

Then I ran find /var/log -size +1M,
These returned me the files that are larger than 1mb i got lots of files and i also got find:’/var/log/chrony’: permission denied ,  find:’/var/log/private,sssd,speech-dispatcher,gdm3’:permission denied also /var/log/syslog,/var/log/dpkg.log …..etc 

Then I ran find / -name "passwd" 2>/dev/null,
It returned me all “passwd” name files and directories like /usr/share/bash-completions/passwd,/usr/share/lintian/overrides/passwd….etc basically it search entire linux filesystem for files or directories named exactly passwd while hiding the error message.


## One thing I can now explain without notes

A SOC analyst can use grep to search authentication logs for failed events, By checking entries containing "Failed password" and "sshd", the analyst can identify failed SSH login attempts. If the analyst needs to locate authentication log files among hundreds of files, they can use find. therefore, grep searches inside files, while find locates files and directories.  

## What I'll review tomorrow
Tomorrow I will study tail -f, less, wc, sort, 
uniq and practice piping commands together.

