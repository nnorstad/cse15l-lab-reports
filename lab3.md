# Lab 3: Researching Commands
<img width="507" alt="researching frog" src="https://user-images.githubusercontent.com/130105980/236717627-ab2ce18b-4bbf-4749-a6fb-def148fcd0a8.png">

## Chosen Command: grep

**grep -c: counts the number of lines where a specified pattern occurs**

Example 1a:

Command:
```
$ grep -c ".txt" find-results.txt
```

<img width="518" alt="Screen Shot 2023-05-08 at 11 48 17 AM" src="https://user-images.githubusercontent.com/130105980/236906932-47f33d3d-9f42-4601-90d2-6aa6a0041c8a.png">

As we can see from the picture, this command is an easy way to count the number of lines that match with the specified string we input. Another way would be to put all the matching lines in a file then call wc, but this would require two commands, not one. Calling grep -c is a more efficient way to count lines in this specific context where all the lines end with the same string.

Example 1b:

Command:
```
$ grep -c "government" find-results.txt
```

<img width="552" alt="Screen Shot 2023-05-08 at 11 56 22 AM" src="https://user-images.githubusercontent.com/130105980/236908692-091a177a-11e7-4596-bbea-307fa80fcc10.png">

The file find-results.txt contains the output from the command
```
$ find technical/ > find-results.txt
```
This file contains many .txt file paths. Our grep -c call returned all the paths that contain *government*. Again, this command is quicker than using word count after commiting all matching paths to a separate file.

**grep -A n: returns line matching input (A) and n lines after**

Example 2a:

Command:
```
$ grep -A 1 "government/Media/An" find-results.txt
```

<img width="660" alt="Screen Shot 2023-05-08 at 12 06 59 PM" src="https://user-images.githubusercontent.com/130105980/236910767-57fe555e-cc1e-403a-a9ee-ad6c6b96596f.png">

This command is used to search for a particular string and return the line containing the string plus n lines after. In the above example, we printed one line after searched line. 

Example 2b:

Command:
```
$ grep -A 1 "government/Media/A" find-results.txt
```

<img width="619" alt="Screen Shot 2023-05-08 at 12 10 08 PM" src="https://user-images.githubusercontent.com/130105980/236911419-5a0d3138-cd6a-4f5f-86a3-9c4a69c678e1.png">

In this example, we changed out search input and we can see that our output changed too. This search gives a more comprehensive idea of how grep -A n performs in different contexts. We can see what happens if two sequential lines match our search criteria: both are printed and the line following the second is printed after. We can also see what happens if there is a line separating two lines that match our search criteria: four lines are printed with no break, with lines 1 and 3 matching our search and lines 2 and 4 being our n extra printed lines.

**grep -v: returns all lines that *do not* match the search criteria**

Example 3a:

Command:
```
$ grep -v "government" find-results.txt > unmatched.txt
```
The output of this command is stored [here](unmatched.txt). It's quite a long output, so it would be difficult to show in a single screenshot. If you look carefully through the file, you can see that there is no output line with the string "government". This file was derived from [find-results.txt](find-results.txt), which we can see contains lines with "government", so the grep -v command clearly excluded all lines with "government".

Example 3b:

Command:
```
$ grep -v "biomed" unmatched.txt > unmatched2.txt
```
The output of the command is stored [here](unmatched2.txt). Again, the output is a little too long to include as a screenshot, but looking at the file, we can see it is the same as the previous result, but this time it excludes path names with "biomed". We can see an interesting feature of this command with these two examples. We are able to further modify lists that have already been modified. We could use this to narrow down a search by excluding certain terms.

**grep -n: returns lines matching search criteria and the line they occur in**

Example 4a:

Command:
```
$ grep -n "plos" unmatched2.txt > lines.txt
```
This is another long output so we'll store it [here](lines.txt). If we take a look at the link, we can see that all the matching lines and their line numbers are stored in this file. While it might be hard to imagine how this could be useful given that the paths in this particular example were orginially grouped together, this command would likely be more useful in larger files where locations of certain lines are unknown.

Example 4b:

Command:
```
$ grep -n "8" plos-only.txt
```

<img width="467" alt="Screen Shot 2023-05-08 at 4 15 05 PM" src="https://user-images.githubusercontent.com/130105980/236957017-5d258309-8c94-46f1-a8e9-16e5e5c00eda.png">

To get this output, we first created a file using the following command:
```
$ grep "plos" unmatched.txt > plos-only.txt
```
This isolated all path names that matched the search "plos" (this is similar to the command above, but this created a file with no line numbers associated with our search output). We could then call grep -n to find all of the outputs containing "plos" that also contain the number 8. This printed all the lines and the path names associated with our search. We get a better idea of how grep -n can be useful because our desired data was not grouped together. grep -n allows us to find the location of certain data in a file.


Works Cited:
[GeeksforGeeks](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
