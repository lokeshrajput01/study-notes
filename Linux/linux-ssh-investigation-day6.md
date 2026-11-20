# Linux Mini-Lab — SSH Investigation
**Date:** 20 November 2026
**Week:** 5, Day 6

## What I understood
Auth.log stores authentication related or security related log events.
Failed login entries contain user,ip address,port  it tells us about user, its ip and port.
It looks like e.g., Failed password for invalid user wronguser from —- ip —--port.
Soc analyst look for username is one account targeted repeatedly or many usernames being tried. Then source ip attempt coming from one ip or many. Then time patterns attempt to happen rapidly or repeatedly. Then attempts count as there are many failures within a short period. Then successful login did successful login occur after repeated failures?

## What confused me
The total number of failed-password log lines confused me, that also includes the previous attempts, not just the attempt generated during my lab. This confused me the first time I saw it.

## Lab output

First i ran this three commands in ubuntu terminal one after one,
sudo systemctl status ssh
sudo systemctl start ssh
sudo systemctl enable ssh
This command checks ssh service is running or stopped, and the second command starts the ssh service immediately so our ubuntu machine can accept ssh connections, then the third command configures ssh to start automatically when ubuntu boots.

After this i open second ubuntu terminal in that i ran this two commands ssh wronguser@localhost
ssh lokesh@localhost
And type wrong password twice for each command.

After this i returned to the first terminal and run this commands as below,

I ran sudo tail -20 /var/log/auth.log,
This command returned me the  latest 20 authentication log events,
Like session opened/closed for user, invalid user,failed password,pam_unix (sshd auth): check pass; user unknown/user(lokesh) and authentication failure…etc lines.

I ran sudo grep -ai "failed" /var/log/auth.log | tail -20,
It returned me the last 20 lines matching “failed”. In these lines i found failed to activate service,timed out, password check failed for user(lokesh),failed password for invalid user wronguser from —-ip —-port and in last failed password for lokesh from —- ip and —port.

i ran sudo grep -ai "invalid user" /var/log/auth.log | tail -10
This returned me only four lines in this lines i found the “invalid user”
The first line had invalid user wronguser from — ip —port,
The second and third line had failed password for invalid user wronguser from —ip —-port
In the fourth line i saw lokesh: tty;pwd; user and command. 

i ran sudo grep -ai "failed" /var/log/auth.log | wc -l
This returned 29 matching lines containing the word "failed". These lines do not necessarily represent 29 failed SSH login attempts because they can include other types of failures. 

sudo grep -ai "failed" /var/log/auth.log | sort | uniq -c | sort -rn | head -10
This returned me first ten lines,
The first three lines had  lokesh: tty;pwd; user and command. 
Then in the fourth line i saw a failed password for lokesh from — ip to —port.
Then in the fifth line I saw a password check failed for user (lokesh).
Then in sixth line i saw failed password for lokesh from —ip —port
Then in seventh line i saw password check failed for user (lokesh)
Then in eight and ninth line i saw failed password for invalid user wronguser from —ip —port
Then in the tenth line i saw failed to activate service.

I saw 1 before every line, which means each identical log entry appeared only once in the output. uniq -c counts identical consecutive lines after sorting. 


## Mini Investigation Report
**Date:** 20 November 2026
**System:** Ubuntu VM localhost

**What I did:**
I ran ssh wronguser@localhost  and entered the password wrong twice.
I also ran ssh lokesh@localhost and entered the password wrong twice.

**What I found:**
I found Session opened, session closed and i also found invalid user wronguser form — ip — port.check pass, user unknown and authentication failure, logname ,uid,euid,tty,ruser
I found Failed password for invalid user wronguser from — ip —port.
Also found Failed password for lokesh from — ip port — 
Password check failed for lokesh.

**Key findings:**
I found two failed attempts for both and the two users are wronguser and user(lokesh),
I found two intentional failed login attempts for each username. The attempts originated from localhost. I did not observe a successful login from these test attempts. 

**Conclusion:**
This is not suspicious because in a real environment even a small number of failed attempts gets logged and monitored because repeated patterns from external IPs would indicate a brute force attempt. 

## One thing I can now explain without notes
The failed SSH login look like this in auth.log,
Failed password for invalid user wronguser from —- ip —--port.
Password check failed for the user.
Each failed SSH login entry in auth.log shows the username attempted, source IP address, port, and whether the user exists on the system. 

## What I'll review tomorrow
Tomorrow is OverTheWire Bandit levels 1-8.

