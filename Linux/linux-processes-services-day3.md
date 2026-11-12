# Linux Processes and Services
**Date:** 12 November 2026
**Week:** 5, Day 3

## What I understood

Every running program is a process and each has a PID(process id).
Every process running in linux gets a unique identifier called a PID(process id).
Ps aux shows all running processes, it includes user,pid,%cpu,%mem,stat,command etc.
top is the live view of processes that updates every few seconds.
htop is the better version of top,more visual and it is the interactive process monitoring tool for linux.
kill PID sends a termination signal (SIGTERM by default), requesting that the process stop. Usually, it terminates. 
Systemd linux commonly used it to manage the services,systemctl is the command used to interact with it.
Journalctl is used to view system log managed by systemd. 

VSZ — virtual memory size, total memory the process could use

RSS — resident set size, actual RAM the process is currently using

TTY — terminal the process is attached to, ? means it has no terminal (background service)

## What confused me

Top and htop confused me today and also systemctl and journalctl confused me a little-bit.

## Lab output

When I run ps aux in the linux terminal, it returns me the user,pid,%cpu,%mem,vsz,rss,tty,start,time,command these columns.

User column has root,systemd+,message+,avahi,polkit,syslog,_chrony,lp,rtkit,cups-br+,colord and lokesh in this column i saw most of root and lokesh, this column basically tells which user is running the process.

In the PID column I saw the process id’s. Like 1,2,3,4….etc.
In the %CPU column I saw the total cpu usage. Like 1.7,0.1,0.2,0.3,.....etc.
In the %MEM column I saw the total memory usage.  Like 0.4,0.5,0.3,....etc.
In the STAT column I saw the process stat. Like Ss,S,I<,I….etc.
In the command column I saw programs/commands that are running. Like /usr/lib/systemd/systemd…..,[kthreadd],.......etc.
In the start column I saw the start time and in the time column I saw the time.

And I also saw the VSZ,RSS,TTY but i dont know what they are.i saw there 0,? And some 4-5 digit numbers.

**After that i ran ps aux | grep ssh,**

I saw 3 running processes for ssh and i saw similar columns.like user,pid,%CPU,%MEM…etc

**After that i ran top,**

First i saw the information like top,user,load average,tasks,total,running,sleeping,stopped,zombie,%cpu,us,sy,ni,id,wa,hi,si,st,mib mem,free,used,buff/cache,mib swap,free,used,avl. Mem,... etc

After that I saw pid,user,pr,ni,virt,res,shr s,%cpu,%mem,time+command.

Top is basically a live view of a process that updates every few seconds.

When I ran htop it basically returned me the more interactive and more visual monitoring,basically it is the better version of top.

I saw 0,1,mem,swap candle bars like in the square brackets, then next to it I saw tasks.thr,kthr,running,load average and uptime.
Then below that i saw main i/o and below that I saw pid,user,pri,ni,virt,res,shr s, cpu%, mem%, time + command.
And it is changing continuously.
And it is more colorful than the top and in the bottom I saw options like help,setup,filter…etc.

**After that i ran this command sudo systemctl status ssh**

then i saw Ssh.service,loaded,active,triggeredby,docs etc information.
Then I ran this command: sudo systemctl start ssh and I saw nothing but it basically starts the ssh service.
Then I ran this command: sudo systemctl status ssh now I see the ssh service is started or running. It showed active(running) and time and date, in the active section before it was inactive(dead). And i saw this information like ssh.service,loaded,active,invocation,triggeredby,docs,process,main pid,tasks,memory,cpu,cgroup.etc

Then I ran this command: sudo systemctl stop ssh I saw nothing but it stopped the ssh service.
Then I ran this command: sudo systemctl status ssh and I saw the ssh service is inactive(dead) means stop. And I saw this information like ssh.service,loaded,active,duration,invocation,triggeredby,docs,process,process,main pid,mem peak,cpu.etc.

Then I ran this command: sudo systemctl enable ssh then I saw this information like  synchronising state of ssh,service with sysv service script with …..
Below that i saw executing,created symlink,created symlink etc.

Then i ran this command: journalctl -u ssh --no-pager | tail -20,
It displayed SSH service logs, including startup, listening addresses, shutdown, and termination messages. I observed that SSH listens on port 22 for IPv4 and IPv6. Signal 15 means SIGTERM, which requests process termination. 

After that I ran sleep 100 & it basically means sleep 100 runs a command that waits for 100 seconds and the & runs it in the background and in my terminal I saw its process id (PID).

Then i ran ps aux | grep sleep and i saw two lines that contained information like user,pid,time,....etc and in the end i saw sleep 100 and sleep.

Then I ran kill [pid]. I typed the pid given after creation. I saw there is no such process and [1]+ done, 
The sleep 100 process had already finished before I tried to terminate it using kill. 
The [1]+ Done message indicated that the background process had completed naturally. 
Therefore, I couldn't verify termination using kill in this attempt.

I also practised with sleep 300 &. This time, I observed [1]+ Terminated sleep 300, which indicated that the background process was terminated. 
I verified it using ps aux | grep sleep and confirmed that sleep 300 was no longer running.


## One thing I can now explain without notes

The process is nothing but every running program.
Ps aux shows all running processes.
Kill stops processes by its PID.
Top shows us the live view of the process that changes every few seconds and htop is a better version of top. It has more visuals than the top.

## What I'll review tomorrow
Tomorrow I will study the investigator's toolkit —
grep, find, tail -f, less, wc, sort, uniq.

