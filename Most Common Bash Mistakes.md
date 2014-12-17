Most Common Bash Mistakes
===================
The following is a list of common mistakes I've seen newcomers make. 

----------

#### Fixing "No such file or directory" Errors

This could be due to invalid file path, insufficient file permissions, and or invalid file contents.
```
ls -al file
```
This will show you whether the file is where you think it is. It will also show you permissions. 
If you opened/created the file under a different operating system, convert file to unix with following...Convert and replace a.txt. Convert and replace b.txt.
```
dos2unix a.txt b.txt
```
For more info...http://goo.gl/fE2Y2v.

#### Bash on multiple machines
You need to run a bash script on several machines, but bash is not always in the same place.
```
#!/usr/bin/env bash.
```

####  Current Directory Is Not in the $PATH
You've checked a million times. Permissions are correct, script works, but when you run the script you get
```
bash: script.sh: command not found
```
Either run script via 
```
./script.sh
```
Or set current directory to be in your **$PATH**
```
PATH="${PATH}:$HOME/bin"
```

#### Do not name your script test
You're welcome.

#### Exported Variables are included in the environment of the invoked shell script
>- Exported environment variables are not globals that are shared between scripts. 
>- They are a one-way communication. 
>- All the exported environment variables are marshaled and passed together as part of the invocation of a Linux or Unix (sub) process (ie fork).
>- There is no mechanism whereby these environment variables are passed back to the parent process. 
>- Remember that a parent process can fork lots and lots of subprocesses…so if you could return values from a child process, which child's values would the parent get?)

#### Variable Assignments

Become a power user of grep. Following searches for log records from a specific ip address in the output of your tail.
```
TEST_VAR=$VAR1 $VAR2
```

> **Tip:** You need quotes around the righthand side of the assignment to $TEST_VAR, otherwise you will see **command not found** error.

#### Debugging Scripts
You can't figure out what's happening in your script and why it doesn't work as expected.
```
Add set-x to the top of the script when you run it. 
```
This will enable xtrace to show you problems in your script.

#### Never do rm -rf /
You will lose your wife, kids, and mortgage. Never means Never!!!
Never delete files using variables, it may not be what you think it is.

#### Seeing Odd Behavior from printf
Either give the variables an initial value (e.g., 0) or put quotes around the references to them on printf lines.

#### Confusing Shell Wildcards and Regular Expressions
You use regular expressions for grep, sed, and bash, but they mean different things depending on the context.
 
 Shell pattern matching is performed by:

| examples    
| :-------  
| Filename globbing (expansion such as *.txt) 
| == and != operators for [[    
| ${parameter/pattern/string}     

http://rubular.com is an excellent resource I use all the time for reg ex composition.
