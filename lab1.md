# Lab 1 Tutorial

## Downloading Visual Studio Code

To access a remote server, we must begin by downloading Visual Studio Code. Downloading Visual Studio Code can be accomplished by following these simple steps:

1. For a mac, either follow this [link](https://code.visualstudio.com/download) or search *download VS code* on google and follow the first link. Click on the button below the apple symbol.

![Image](https://user-images.githubusercontent.com/130105980/230967016-3e48df3b-da13-40bc-a1bd-6db18584b7ed.png)

2. This will open a zip file. Once the file has downloaded, open it. Double click the file labeled *Visual Code Studio* and click *open* when prompted.

3. Once VS Code is open you will see the following screen:

![Image](https://user-images.githubusercontent.com/130105980/230972298-b41c1633-03aa-4f26-b860-7b71f0c9a645.png)

## Accessing a Remote Server 

Begin by logging into the course-specific account for ieng6 in the terminal of VS code. To do this, first select *Terminal* from the menu on the upper most part of the screen and then select *New Terminal* from the drop down menu. 

Type *ssh cs15lsp23(...)@ieng6.ucsd.edu* into the terminal and press enter, where (...) is replaced with your course-specific username. When prompted, enter your course-specific password and press enter again. If your access was successful, you should see confirmation of the login similar to the screen below.

![Image](https://user-images.githubusercontent.com/130105980/230979637-75aab84f-8c48-4def-beb5-d0f7052c2c38.png)

## Running Commands

Once you have access to the remote server, you can run a variety of different commands. Some examples include:
- pwd : print working directory
> to execute, type pwd into the command line; this command accesses the working directory 
- cd <path> : change directory to the given path
> to execute, type cd followed by the desired path; this command changes the current working directory, confirm the change by using pwd
  
Example, running the pwd command:
  
 ![Image](https://user-images.githubusercontent.com/130105980/230988489-1d0ffb08-8c41-419e-bfae-d1f2aa16c78b.png)

