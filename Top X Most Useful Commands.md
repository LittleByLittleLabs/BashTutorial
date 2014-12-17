Top X Most Useful Bash Commands
===================


Hey! Over the years, I've found myself using some parts of Bash more than others. Below is a list of the more oftenly used parts of **Bash**. I encourage you to keep your mind open and consider this as a jump start into your journey with **Bash**.

----------

#### <i class="icon-file"></i> How To Declare a Bash Alias

Tired of typing the same command over & over. Create an alias...
```
# alias alias_name="command_2_run"
alias ll="ls -lhA"
```
note: spaces between bash elements will cause errors.

To see a list of all available aliases:
```
alias
```
To unset an alias
```
unalias ll
```
You generally want to set aliases in **~/.bashrc** and **~/.bash_profile**. Remember to use **source ~/.bashrc** for the changes to take effect. Otherwise your changes will take effect the next time you open a terminal.

> **Tip:** Git commands make great candidates for aliases.

####  Search file in a directory

```
find . -name file_name.txt
```
If you see errors due to not having privileges during your search, consider adding prefix sudo. If you're not sure where the file can be in the filesystem, this will search the entire filesystem...
```
sudo find / -name file_name.txt
```

#### Command gone wild

If you find the bash terminal to be unresponsive, consider <kbd>Ctrl+C</kbd> to kill the command. 

Another popular key combination I use is <kbd>Cmd+K</kbd>. This will clear your screen, very useful when you are troubleshooting / viewing log entries.

#### Tail last n lines of a file

Often you will need to look thru log files in order to troubleshoot your applications/services. Consider...
```
tail -n 50 -f /var/log/application.log
```
The **cat** command reads one or more files and prints them to standard output. 
```
cat file1
```
I also use less in the event where I don't need to modify the file, after all, opening a file with vim or editor increases the likelihood of accidentally making a change, which can cause issues in production environment.
```
less file2
```

#### Grep

Become a power user of grep. Following searches for log records from a specific ip address in the output of your tail.
```
tail -f /var/log/application.log | grep 24.10.160.10
```

> **Tip:** Remember to use **man command_name** for more info/examples of how to use a particular command.

#### List / Search running processes
**ps** gives a snapshot of the current processes. **ps** command is your friend. The following will list all java processes which are running.
```
ps aux | grep java
```

#### List / Search running processes
Ever did something and forgot how. **history** to the rescue
```
history
```

#### Permissions, Permissions, Permissions
Confident you have the right command but still not working? It's likely a permissions issue. Bites the best of us.
```
ls -al .
```
|   Symbolic Notation | Octal Notation	          | English              |
 ----------------- | ---------------------------- | ------------------
| `----------`       | `0000`                     | `no permissions` |
| `---x--x--x`       | `0111`                     | `execute` |
| `--w--w--w-`       | `0222`                     | `write` |
| `--wx-wx-wx`       | `0333`                     | `write & execute` |
| `-r--r--r--`       | `0444`                     | `read` |
| `-r-xr-xr-x`       | `0555`                     | `read & execute` |
| `-rw-rw-rw-`       | `0666`                     | `read & write` |
| `-rwxrwxrwx`       | `0777`                     | `read, write, & execute` |

> **Tip:** You likely want to set 755 for executable scripts .

#### Understanding your shell env
> - All the programs that run under Linux are called as processes. 
> - Processes run continuously in Linux and you can kill or suspend different processes using various commands. 
> - When you start a program a new process is created. This process runs within what is called an environment.  
> - Every program runs in its own environment. You can set parameters in this environment so that the running program can find desired values when it runs. 

Setting a particular parameter is as simple as typing VARIABLE=value . This would set a parameter by the name VARIABLE with the value that you provide. 

**$PATH** 
 This is a very important environment variable. 
This would add the new directory to the existing PATH value.
```
PATH=$PATH:/newdirectory
```
