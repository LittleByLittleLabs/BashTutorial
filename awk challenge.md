AWK Challenge
----------
1) Given the following input
``` 
1 5 23 8 16
44 3 5 2 8 26
256 291 1396 2962 100
-6 467 998 1101
99385 11 0 225
```
Write a script which will output the largest value in the array.

2) Given the following input data in a file called input.data...
```
xbox_one 33 350
ps4 15 300
iPad 20 200
pencils 50 .50
iPhone6 Plus 40 200
```
Create a report called product.report which looks like the following
```
Report created on Monday Feb xx hh:mm:ss PST 2015 by your_name

Product Name     Quantity     Price
____________     ________     _____

xbox_one         33           350
ps4              15           300
iPad             20           200
pencils          50           .50 
iPhone6 Plus     40           200   
```

3) Given the following awk script, print out the usage as comments
```
BEGIN {
    while ((c = getopt(ARGC, ARGV, "ce:svil")) != -1) {
        if (c == "c")
            count_only++
        else if (c == "s")
            no_print++
        else if (c == "v")
            invert++
        else if (c == "i")
            IGNORECASE = 1
        else if (c == "l")
            filenames_only++
        else if (c == "e")
            pattern = Optarg
        else
            usage()
    }
```

For example:
```
# x.awk --- do something in awk
# Options:
#    -x      does blah blah
```

4) Write a script which generates word usage counts for the following text:
```
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
```

Sample output:
of: 5 
the: 6
.... you get the idea

