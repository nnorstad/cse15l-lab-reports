# Lab 5: Debugging Scenario and Reflection #

## Bug! ##
Hi! I'm doing write a bash script on my Mac (Monterey) and I'm working VS code. 
I'm trying to get my code to perform a grep command given some command line input,
but I'm not getting the output I expected. I've created some test files to make sure
the code works as intended, but the grep command doesn't return anything when it should.
It is also giving me an error that the file does not exist when I enter a file path. I 
have tried using cd and pwd, and I'm sure I'm in the correct file. I still think I may
have an error with my file organization.

<img width="600" alt="Screen Shot 2023-06-05 at 10 56 59 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/2444dc23-2da8-44a9-ba87-f6340d76c11e">
<img width="453" alt="Screen Shot 2023-06-05 at 11 02 56 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/b394102f-9738-4b97-a5c6-b0a8246f6d9c">

I'm searching for "this" in my file, and I know the file contains the word (shown below), but the output
file is empty when I run the code (as shown above) and I get an error message.

<img width="546" alt="Screen Shot 2023-06-05 at 11 03 13 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/2e524b86-25b4-46b3-91b4-1ad223f4f6f3">
<img width="499" alt="Screen Shot 2023-06-05 at 10 58 22 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/0cbe7294-1597-4f46-b1d1-729d096be552">

There aren't any compile errors, but it also doesn't show my intended error
message for when a file doesn't exist, so I'm not sure what I'm doing wrong. 

## Response ##
Hello! From your screenshots, it seems like you have a simple error to fix. I suggest you 
take a look at how to use variables in bash. When do we use quotes in bash, and when would
it be useful to use other syntax?

## Fix ##

<img width="392" alt="Screen Shot 2023-06-05 at 11 06 21 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/064b485e-3274-4a3e-8226-9d743ece7f0e">
__________________________________________

<img width="523" alt="Screen Shot 2023-06-05 at 11 06 35 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/1aaaa6f0-2663-468f-b30e-4fd7e625ad04">

Thanks for the help, I now realize I used quotes to reference my variables, so bash was
looking for a file named "path", not the name of the input file. I deleted the quotes and
added $ in front of the variables I wanted to reference and now the code runs correctly!

## Summary ##
The bug was triggered by the student mistakenly using quotes to reference variables. 
Although it seemed like there may be an error with the file structure or the directory,
this was a misleading output and shows how not all errors may be directly caused by the 
error message they produce. This shows the importance of thoroughly testing code.

File Structure:

<img width="277" alt="Screen Shot 2023-06-05 at 11 12 26 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/41924d29-27b0-4544-b9ca-53568b4fd45d">

Before:

<img width="600" alt="Screen Shot 2023-06-05 at 10 56 59 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/2444dc23-2da8-44a9-ba87-f6340d76c11e">
<img width="453" alt="Screen Shot 2023-06-05 at 11 02 56 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/b394102f-9738-4b97-a5c6-b0a8246f6d9c">

After Fix:

<img width="392" alt="Screen Shot 2023-06-05 at 11 06 21 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/064b485e-3274-4a3e-8226-9d743ece7f0e">
__________________________________________

<img width="523" alt="Screen Shot 2023-06-05 at 11 06 35 PM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/1aaaa6f0-2663-468f-b30e-4fd7e625ad04">

The bug was triggered using the command in the above screenshot used in the description
of the bug. The bug was fixed by getting rid of the quotes around the variables in the
if statement and putting $ in front of both variables.

## Reflection ##
I ended up learning far more in this class than I could have imagined.
Something that really stands out to me, though, is lab 7. I always love
doing any work that gives me some insight into how every day technology works.
I loved learning about some of the background operations of an autograder and I 
felt incredibly accomplished when it worked. I know I'm still very new in my 
computer science journey, but I think it is so fascinating to learn how 
tools I use all the time are programmed. Even though they are highly simplified 
versions of the technology, I feel like I got a great overview of how these
 technologies are implemented and it made me feel really excited about the idea
  of having a career in programming. 

