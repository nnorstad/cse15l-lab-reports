# Lab Report 4: VIM and File Editing #
## Step 1: Logging into ieng6 ##
<img width="777" alt="Screen Shot 2023-05-22 at 8 51 00 AM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/1eb4d427-98fe-4b00-8efb-97ce0f8cfd93">

We can see here what it looks like to successfully log into ieng6. Usually, it will require password authentication, but during week 7 lab we configured our accounts so we no longer have to type in our passwords. To access the ssh command, I used the history keyword in the terminal as follows.
```
$ history | grep "ssh" <enter>
```
This command searched the command line history for all commands including ssh. The output of this command was a list of all the recent commands that included ssh, which allowed me to easily acceess my ieng6 username. Creating an ssh key and using the history keyword allows a user to login to ieng6 without needing to remember their username and password. After searching for ssh commands, I copied the desired command using cmd C, then pasted it in the terminal with cmd V, finally logging in by pressing enter.

## Step 2: Forking and Cloning the Repository ##
<img width="615" alt="Screen Shot 2023-05-22 at 9 17 00 AM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/f4ffad85-1305-4962-a557-cdfc11f2cfa0">

The next step is forking and cloning the repository for lab 7. We do this by using the following command.
```
$ git clone https://github.com/ucsd-cse15l-s23/lab7 <enter>
```
To enter the directory we can type
```
$ cd lab7 <enter>
```
At this point we are inside the lab 7 directory. 

## Step 3: Running Tests ##
<img width="598" alt="Screen Shot 2023-05-22 at 9 26 30 AM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/611b1f00-d429-4cc2-a7c7-d5c2874f3be8">

The output in the screenshot shows that the tests failed. To get this output, we used the following command.
```
$ bash test.sh <enter>
```
The test.sh file contains the jUnit test commands so we can run the tests without writing a lengthy command. 

## Step 4: Editing the Buggy Code ##
<img width="601" alt="Screen Shot 2023-05-22 at 9 38 12 AM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/8992fc28-a8fd-4798-8c02-069bf9c60cf7">

We need to edit the fourth line from the end of the file, and the cursor was already about halfway down the file. To edit this line I pressed the down arrow 14 times and the right arrow 11 times. After, I pressed r to replace the 1 in index1 with 2 so the code read index2.
```
<down><down><down><down><down><down><down><down><down><down><down><down><down><down>
<right><right><right><right><right><right><right><right><right><right><right> r2
```
After, I saved the changes in the file by using the command below.
```
:wq <enter>
```
This saved and exited the file and returned us to the terminal.

## Step 5: Running Tests Again ##
<img width="388" alt="Screen Shot 2023-05-22 at 9 42 12 AM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/e4062058-9543-4979-93f0-7c75ca1c0ff9">

We have successfully edited the file so the code passes the jUnit tests, which is clear from the output from the tests. To run the tests again, I pressed the up arrow twice and pressed enter. This accessed the test command from the previous time we ran it so we didn't have to right the command again.
```
<up><up><enter>
```

## Step 6: Commit and Push Changes to Github ##
<img width="525" alt="Screen Shot 2023-05-22 at 9 49 36 AM" src="https://github.com/nnorstad/cse15l-lab-reports/assets/130105980/95708635-95b8-4c3c-b9a9-56b82dbae4ac">

To commit the changes we made to github, we first used the command below.
```
$ git add ListExamples.java <enter>
```
This tells github which changes we want to be committed to the repository. Next we committed the changes by using the following command.
```
$ git commit -m "debug" <enter>
```
This command specifies that we are committing with a message. The final step is to push the changes to our github account.
```
$ git push <enter>
```
This is a simple command and after this we have successfully edited and saved our file.

