# Investigator's Toolkit Part 2

**Date:** 19/11/2026

**Week:** Week 5, Day 5

## What I understood
tail shows the end of a file.
tail returned last 10 lines by default.
tail -n 20 returned last 20 line
tail -f follows the file live and shows new line as they appear.

less read file page by page and also it is better than cat for large files.

wc counts lines, words and bytes. wc -l counts lines.

sort it basically sorts lines by alphabetically or numerically
sort alphabetical sort
sort -r reverse sort 
sort -n numerical sort

uniq it removes or counts duplicate lines and it must be used after sort because it only removes adjacent duplicates.
sort file.txt | uniq removes duplicates.
sort file.txt | uniq -c counts how many times each line appears.
sort file.txt | uniq -c | sort -rn count duplicates and sort by most frequent.

pipes | sends output of one command to another.


## What confused me
when i ran this two commands,
grep -ai "failed" /var/log/auth.log | sort | uniq -c | sort -rn | head -10
grep -ai "error" /var/log/syslog | sort | uniq -c | sort -rn | head -10
the output really confused me specifically for the second command, like it contain lot of information that's why.

## Lab output
When i ran tail /var/log/syslog in ubuntu terminal, 
I got the last 10 lines. By default the lines are containing information like log entry timestamp then ubuntu-lab systemd[1],geoclue[2016]: then information like stopping user…., run-user…..,user-runtime-dir …,etc etc. 

Then i ran tail -n 20 /var/log/syslog,
The last 10 lines were also included in this output, along with 10 earlier lines and with same information like earlier.

Then i ran sudo tail -f /var/log/auth.log,
I got few lines same like the previous lines like the log entry timestamp, ubuntu-lab gdm-password,gdm-launch-environment,...... etc different for every line and next to it information like unlocked login keyring,removed session c1……etc different on each line.
And after I ran ssh localhost in the new terminal, I saw new lines appear below the existing lines.
Like accepted password for me from —- port then on next line pam_unix then new session….etc-etc information.
-f monitors new log entries in real time.

Then i ran less /var/log/syslog,
I got to read the file page by page in that i search /error and i found error highlighted and i use n for next match and b moves back one page and uses q to quit.  

After that i ran wc -l /var/log/syslog,
I got 39937 /var/log/syslog. This basically means the total line count which is 39937.

Then i ran grep -ai "failed" /var/log/auth.log | wc -l,
I got 20. It means there are 20 lines containing the word “failed.”

After that i ran grep -ai "failed" /var/log/auth.log | sort | uniq -c | sort -rn | head -10,
I got the 10 most frequent matching log lines. The number at the beginning shows how many times each identical line appeared. I also saw identical lines that had failed and Failed in it.
grep -i matches different letter cases, sort and uniq are case-sensitive by default. That's why Failed and failed appear as separate entries.

Then i ran grep -ai "error" /var/log/syslog | sort | uniq -c | sort -rn | head -10,
I got the first 10 lines that have “error” in it and i also saw same like previous output that 1 is at the start of every line,but it is more confusing than the  grep -ai "failed" /var/log/auth.log | sort | uniq -c | sort -rn | head -10 it has lots of information but i can see error,ERROR,Error words appearing in everyline. I really cannot understand all this information available here.
sort groups identical lines and uniq -c counts them. 

After that i ran this grep -ai "session opened" /var/log/auth.log | wc -l
I got 172. It basically means there are 172 lines that contain “session opened” but it doesn’t mean 172 different users.

Then i ran grep -ai "session opened" /var/log/auth.log | sort | uniq -c | sort -rn | head -5
I got first five lines, in this lines i saw session opened for user,root user lokesh ….etc 

Then i ran cat /var/log/syslog | grep "error" | sort | uniq | wc -l
I got grep: (standard input): binary file matches and below that 28.

Then i ran cat /var/log/syslog | grep -a "error" | sort | uniq | wc -l
I got 208 that basically means there are 208 distinct matching lines after sorting and removing duplicates.
i used grep -a "error" without -i, so it matched lowercase error, not necessarily ERROR or Error.
Also, -a tells grep to process the input as text. It doesn't make the search case-insensitive.

SOC relevance: These commands help analysts monitor authentication activity, identify repeated log messages, count events and investigate system errors. 


## One thing I can now explain without notes
pipes | basically sends output from one to another command.

sort used to sort lines alphabetically or numerically while uniq used to remove or counts same lines.

tail gives us last 10 lines and less reads file page by page

## What I'll review tomorrow
Enable and verify the SSH service, perform intentional failed login attempts, and investigate the authentication events in /var/log/auth.log using grep and tail.
