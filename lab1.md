# Lab 1 Tutorial

## Downloading Visual Studio Code

To access a remote server, we must begin by downloading Visual Studio Code. Downloading Visual Studio Code can be accomplished by following these simple steps:

1. For a mac, either follow this [link](https://code.visualstudio.com/download) or search *download VS code* on google and follow the first link. Click on the button below the apple symbol.

<img width="250" alt="mac download" src="https://user-images.githubusercontent.com/130105980/234123361-542aae7c-0e7d-4006-adb8-a50419d0095f.png">

2. This will open a zip file. Once the file has downloaded, open it. Double click the file labeled *Visual Code Studio* and click *open* when prompted.

3. Once VS Code is open you will see the following screen:

<img width="300" alt="VS code" src="https://user-images.githubusercontent.com/130105980/234123816-214a7249-a9ff-4ac2-99fd-a5fc91276230.png">


## Accessing a Remote Server 

Begin by logging into the course-specific account for ieng6 in the terminal of VS code. To do this, first select *Terminal* from the menu on the upper most part of the screen and then select *New Terminal* from the drop down menu. 

Enter the following command into the terminal, where the -- is replaced with your course specific code. Press enter, and when prompted, enter your password.

```
  $ ssh cs15lsp23--@ieng6.ucsd.edu
    (cs15lsp23--@ieng6.ucsd.edu) Password:
  
 ```
If your access was successful, you should see confirmation of the login similar to the screen below.

<img width="400" alt="remote access" src="https://user-images.githubusercontent.com/130105980/230979637-75aab84f-8c48-4def-beb5-d0f7052c2c38.png">


## Running Commands

Once you have access to the remote server, you can run a variety of different commands. Some examples include:
- pwd : print working directory
  ```
  $ pwd
  ``` 
  <img width="400" alt="pwd" src="https://user-images.githubusercontent.com/130105980/230988489-1d0ffb08-8c41-419e-bfae-d1f2aa16c78b.png">

  
- cd <path> : change directory to the given path, confirm the change by using pwd
  ```
  $ cd <path>
  ```
  
- ls : lists all files
  ```
  $ ls 
  ```
  <img width="400" alt="ls" src="https://user-images.githubusercontent.com/130105980/234122758-a7dc2402-0007-440c-960e-47194ab414df.png">
  
  
- ls -a : lists all files, including hidden files
  ```
  $ ls -a
  ```
  <img width="600" alt="ls -a" src="https://user-images.githubusercontent.com/130105980/234122908-da8ba33f-7f1e-4bef-9ed8-153ee65bb0ba.png">
  
  
- cat <file> : prints the contents of one or more files, file is replaced by the path
  ```
  $ cat <file1> <file2>
  ```
  <img width="400" alt="remote access" src="https://user-images.githubusercontent.com/130105980/234121945-cb1529a5-358c-4406-85ee-b0a1d4e848de.png">

  
  


