## Bash Shell Challenge #2

1. Run scripts in a given directory
--------------------
Prompt the user for a directory, then you want to run a all the scripts in it.
```
-> Please enter a directory which contains your scripts:
/home/whatever

Running scripts in /home/whatever...

```

2. Check # of arguments passed to script
---------------------------------
Write a command line program which checks that only 3 arguments have been passed into the script, error otherwise.

Should look something like...
```
➜  ~ ./example_script.sh 1 2 3
Looking good
➜  ~ ./example_script.sh 1 2 3 4
You have exceeded the expected number of parameters
➜  ~ ./example_script.sh 1 2 
You have not entered the minimum expected number of parameters
```
 
3. Input/Output file validation
---------------------------------
Write a script by checking to see if your input file is there before reading from it. You would like to see if your output file has write permissions before writing to it. 
```
!/usr/bin/env bash
DIRPLACE=/tmp
INFILE=/home/me/input.data
OUTFILE=/home/me/output.results 
#...Your code goes here...
```
