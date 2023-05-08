# Lab 3: Researching Commands
<img width="507" alt="researching frog" src="https://user-images.githubusercontent.com/130105980/236717627-ab2ce18b-4bbf-4749-a6fb-def148fcd0a8.png">

## Chosen Command: grep

**grep -c: counts the number of lines where a specified pattern occurs**

Example 1a:

<img width="518" alt="Screen Shot 2023-05-08 at 11 48 17 AM" src="https://user-images.githubusercontent.com/130105980/236906932-47f33d3d-9f42-4601-90d2-6aa6a0041c8a.png">

As we can see from the picture, this command is an easy way to count the number of lines that match with the specified string we input. Another way would be to put all the matching lines in a file then call wc, but this would require two commands, not one. Calling grep -c is a more efficient way to count lines in this specific context where all the lines end with the same string.

Example 1b:

<img width="552" alt="Screen Shot 2023-05-08 at 11 56 22 AM" src="https://user-images.githubusercontent.com/130105980/236908692-091a177a-11e7-4596-bbea-307fa80fcc10.png">

The file find-results.txt contains the output from the command
```
$ find technical/ > find-results.txt
```
This file contains many .txt file paths. Our grep -c call returned all the paths that contain *government*. Again, this command is quicker than using word count after commiting all matching paths to a separate file.

**grep -A n: returns line matching input (A) and n lines after**

Example 2a:

<img width="660" alt="Screen Shot 2023-05-08 at 12 06 59 PM" src="https://user-images.githubusercontent.com/130105980/236910767-57fe555e-cc1e-403a-a9ee-ad6c6b96596f.png">

This command is used to search for a particular string and return the line containing the string plus n lines after. In the above example, we printed one line after searched line. 

Example 2b:

<img width="619" alt="Screen Shot 2023-05-08 at 12 10 08 PM" src="https://user-images.githubusercontent.com/130105980/236911419-5a0d3138-cd6a-4f5f-86a3-9c4a69c678e1.png">

In this example, we changed out search input and we can see that our output changed too. This search gives a more comprehensive idea of how grep -A n performs in different contexts. We can see what happens if two sequential lines match our search criteria: both are printed and the line following the second is printed after. We can also see what happens if there is a line separating two lines that match our search criteria: four lines are printed with no break, with lines 1 and 3 matching our search and lines 2 and 4 being our n extra printed lines.

**grep -v: returns all lines that *do not* match the search criteria**

Example 3a:

Command:
```
$ grep -v "government" find-results.txt > unmatched.txt
```
The output of this command is stored [here](unmatched.txt). It's quite a long output, so it would be difficult to show in a single screenshot. If you look carefully through the file, you can see that there is no output line with the string "government". This file was derived from [find-results.txt](find-results.txt), which we can see contains lines with "government", so the grep -v command clearly excluded all lines with "government".


