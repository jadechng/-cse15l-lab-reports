# Lab Report 1

Hello! For this lab report, we would be walking through the
steps to log into a course-specific account on `ieng6`!
We would be going through 6 steps in this tutorial:
Installing VScodde, Remotely Connecting, Trying Some
Commands, Moving Files with `scp`, Setting a SSH Key and 
Optimizing Remote Running.

***

## Installing VScode
To get started, we would be using the code editor VScode for this course. To download, go to [Visual Studio Code](https://code.visualstudio.com/) and follow the instructions to download for your version of the operating system ie. MACOS or Windows. 

When installed, it should open like this (don’t worry! it might look slightly different on yours depending on your theme and settings): 

![vscode](https://user-images.githubusercontent.com/103202818/162368933-9fffeeaa-aee7-49f0-a179-6e7fbf771928.png) 

***

## Remote Connecting

Now, we would start the process of remotely connecting! 
For Windows users, you will have to complete an additional step of downloading [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse). It is a program that allows your computer to connect to others.

Since I use a MAC device, I get to skip this step:) 

We would then look up our specific course account using this [link](https://sdacs.ucsd.edu/~icc/index.php) 

Returning back to VScode, open a new terminal and input the command: 
`ssh cs15lsp22amd@ieng6.ucsd.edu`

My command consists of the letters `amd` and yours would be different depending on your course-specific account. 

If it's your first time logging in, you may receive a message and just reply `yes` and enter your password when prompted. 

You should see this upon logging in: 
![login](https://user-images.githubusercontent.com/103202818/162369536-7f82dbf3-2ebd-480d-b333-137cda15713b.png)

***
## Trying Some Commands
Now we would try some commands on both the remote server (after ssh-ing) and on your computer: 
* `cd ~` : going back to the home directory
* `ls -a `: Listing all files included hidden ones
* `ls <directory> ` where `<directory> is /home/linux/ieng6/cs15lsp22/cs15lsp22abc`, where the abc is one of the other group members’ username
* `cp /home/linux/ieng6/cs15lsp22/public/hello.txt ~/` : copies the file in that directory
* `cat /home/linux/ieng6/cs15lsp22/public/hello.txt`: displays the contents of the file 

Here is the result I get when I use this command on the remote server: `/home/linux/ieng6/cs15lsp22/cs15lsp22abc`

![image](https://user-images.githubusercontent.com/103202818/162370194-57d29910-111c-48e9-aa65-bdf00f99eb8f.png)

It shows permission denied because I do not have the privileges to enter my peer's server and it's a secure shell.

***
## Moving Files with `scp`

Now we would learn how to move files back and forth from your computer to the remote computer using the command `scp`. 

I have created a file called `WhereAmI.java`, which would tell us the location of the drive. From the terminal in the location that we created the file, we use this command: 

`scp WhereAmI.java cs15lsp22amd@ieng6.ucsd.edu:~/`

Enter your password and then log into the server again using `ssh` and list the files in the server using `ls`. 

As you can see the the file is now on the server!

![image](https://user-images.githubusercontent.com/103202818/162370871-593c722a-b10d-4eb6-9490-7dae991ad355.png)

You can compile and run the code on the remote server now:)

***
## Setting SSH key
As you notice by now, every time we would want to move the files between computers, we would have to enter our password which is time-consuming and tedious. Hence, we use `ssh` keys. 

It creates a public key and a private key. The public key is stored in the server and the private key is sttored on the client (your computer). 

To set it up, enter the command on your computer (client):

`ssh-keygen`

When prompted to enter a paraphrase, DO NOT enter one, leave it empty. 

Now, we have to add the public key to the server:

`$ ssh cs15lsp22zz@ieng6.ucsd.edu`\
`$ mkdir .ssh`\
`$ <logout>`\
`# back on client`\
`$ scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22amd@ieng6.ucsd.edu:~/.ssh/authorized_keys`

Now, we can access the server without entering the password!! yay: 

![image](https://user-images.githubusercontent.com/103202818/162371418-bdfdf5cd-0084-4b09-8584-a2a9e3cf69c7.png)

***
## Optimizing Remote running

Lastly, here are some tips that can make running commands more efficient: 

* You can add the commands in quotes at the end of the `ssh` command to directly run it on the remote computer and immediately exit. 

![image](https://user-images.githubusercontent.com/103202818/162371714-09e51cf1-71d3-4c10-b128-004212aef894.png)

* You can add semicolons to run multiple commands on the same line

![image](https://user-images.githubusercontent.com/103202818/162371946-c8fb7c6e-d796-4e28-96b1-8f7a3c79b624.png)


* You can use up and down arrow keys to recall your previous commands 






















