# Week 1: Lab Report 1
***By Kevin Chan (t-sekai), September 30, 2022***

## Table of Content
- [Week 1: Lab Report 1](#week-1-lab-report-1)
  - [Table of Content](#table-of-content)
  - [Install VSCode](#install-vscode)
    - [Step 1: Download VSCode for your operating system from Download VSCode](#step-1-download-vscode-for-your-operating-system-from-download-vscode)
    - [Step 2: Open VSCode](#step-2-open-vscode)
  - [Remotely Connecting to UCSD Servers](#remotely-connecting-to-ucsd-servers)
    - [Step 1: Get your account information](#step-1-get-your-account-information)
    - [Step 2: Connecting to Remote Server](#step-2-connecting-to-remote-server)
  - [Some Commands You Can Try](#some-commands-you-can-try)
    - [Print Working Directory (*pwd*)](#print-working-directory-pwd)
    - [List (*ls*)](#list-ls)
    - [Change Directory (*cd*)](#change-directory-cd)
    - [Make/Remove Directory (*mkdir / rmdir*)](#makeremove-directory-mkdir--rmdir)
    - [Create File (*touch*)](#create-file-touch)
    - [Remove File (*rm*)](#remove-file-rm)
    - [Concatenate (*cat*)](#concatenate-cat)
    - [Copy (*cp*)](#copy-cp)
    - [Exit (*exit or ctrl-d*)](#exit-exit-or-ctrl-d)
  - [Copying Files with *scp*](#copying-files-with-scp)
  - [Setting an SSH Key](#setting-an-ssh-key)
    - [Step 1: Generate a Key](#step-1-generate-a-key)
    - [Step 2: Copy the Public Key to the Remote Server](#step-2-copy-the-public-key-to-the-remote-server)
  - [Optimize Remote Running](#optimize-remote-running)
    - [Use *Tab*](#use-tab)
    - [Look into Past Commands](#look-into-past-commands)
    - [Use a Script](#use-a-script)

***

## Install VSCode

It is always more efficient to use a good all-in one code editor that can run many different languages and scripts. VSCode is one such editor. Let's get started!

### Step 1: Download VSCode for your operating system from [Download VSCode](https://code.visualstudio.com)

![](vscode_download.png)

Once the installer is downloaded, open it and follow the installation step.
### Step 2: Open VSCode
Open VSCode in your Application folder and begin programming in a great code editor!

![](vscode_empty.png)

***

## Remotely Connecting to UCSD Servers

Why do we want to connect to a secure shell, aka ssh? The remote server can be more powerfull and be in a different operating system that you want to use. We have the Linux operating system on the UCSD computers.

Let's get started by knowing how to connect to the SSH!

### Step 1: Get your account information

The very first step you need to do is to know your CSE 15L server account and set up your credentials.

Go to [Account Lookup](https://sdacs.ucsd.edu/~icc/index.php) and enter your UCSD credentials to log in. Explore the site and find your CSE 15L account username (looks like ex. *cs15lfa21ab*). Also, the website will also prompt you to change your password for the account (it takes time for the server to update your password). Keep a note of your credentials because you will need to use that shortly.

![](ssh_account.png)

### Step 2: Connecting to Remote Server

Open terminal or command line on your computer. Run the following code (remember to substitute the 'username' with your own) :
```bash
ssh username@ieng6.ucsd.edu
```

It will look something like this:

![](ssh_login.png)

Congrats! You've successfully connected to the UCSD Remote Server. If your password isn't working, maybe the server hasn't been updated with your new password yet.

***

## Some Commands You Can Try

It is very important to know your terminal commands! Here are some you can try!

### Print Working Directory (*pwd*)

```bash
#returns the current working directory 

pwd
```
![](pwd.png)

### List (*ls*)

```bash
#returns the visible files in your directory

ls [directory]

#returns both the visible and hidden files in your directory

ls [directory] -a
```
![](ls.png)
### Change Directory (*cd*)

```bash
#change to your intended directory

cd [directory]

#returns to the parent directory

cd ..
```

![](cd.png)

### Make/Remove Directory (*mkdir / rmdir*)

```bash
#creates your intended directory

mkdir <directory>

#removes your intended directory

rmdir <directory>
```

![](mkdir.png)
### Create File (*touch*)

```bash
#creates your intended file


touch <file>
```

### Remove File (*rm*)

```bash
#removes your intended file

rm <file>
```

### Concatenate (*cat*)

```bash
#preview your intended file

cat <file> ... [more files]
```

### Copy (*cp*)

```bash
#copy your intended file to your intended destination

cp <source file/dir> <destination file/dir>
```

### Exit (*exit or ctrl-d*)

```bash
#exits remote server (or current session)

exit
or ctrl-d
```

***

## Copying Files with *scp*

If you want to copy a file from your local computer to the remote server (or vice versa), you will need to use the *scp* instead of the *cp*, which only works in the same system.

```bash
scp <source file/dir> <destination file/dir>
```

Here is an example with UCSD Server:
```bash
#We have WhereAmI.java in the local computer, and we want to copy it to the remote server.

scp WhereAmI.java username@ieng6.ucsd.edu:

#We want to copy it back after some edits.

scp username@ieng6.ucsd.edu:~/WhereAmI.java ~
```

![](scp1.png)

![](scp2.png)

![](scp3.png)

***

## Setting an SSH Key

### Step 1: Generate a Key

```bash
#Running this in your local will create an SSH Key

ssh-keygen
```

The terminal will prompt you which file to save the key in. Press enter for the default location. Next, it will prompt you to enter a passphrase for your key. Press enter for no passphrase.

![](ssh-keygen.png)

Now, you can find *id_rsa* and *id_rsa.pub* in *~/.ssh* on your computer.

### Step 2: Copy the Public Key to the Remote Server

First, log in to your remote server. We want to copy the public key to the .ssh directory (which we need to make) on the server.

```bash
# This will create the .ssh directory to the server

mkdir .ssh
```

Next, exit the server. In local, we want to copy the public key to the directory through the *scp* command.

```bash
# This will copy the public key to the .ssh directory in the remote server

scp /Users/computer_username/.ssh/id_rsa.pub username@ieng6.ucsd.edu:~/.ssh/authorized_keys

# Use your own computer username and cs15l account username.
```

![](ssh_scp.png)

After doing this, you can enter or copy files to the remote server using *ssh* and *scp* without having to enter your password.

![](ssh_noPwd.png)

Congrats you have set up your ssh key! Now, you can access the remote server more efficiently.

***

## Optimize Remote Running

We could be calling identical or similar lines of commands over and over many times. We can optimize and improve our experience by lessening the ammount of lines we have to write. Below, are a few ways to optimize your experience in remote running:

### Use *Tab*

The *tab* button can autocomplete some of the commands. 

> For example, the *tab* button can autocomplete finding the directories in *cd*.
> ```bash
> # Let's say you want to cd Desktop/
>
> cd D
>
> # If you press tab once or twice, the terminal will autocomplete 
>
> cd Desktop/
> Desktop/    Documents/  Downloads/
>
> # You can press tab again for Document
>
> cd Documents/
> Desktop/    Documents/  Downloads/
> ```
> Try it on your own!

Find more example in [Command-line Completion](https://en.wikipedia.org/wiki/Command-line_completion).

### Look into Past Commands

1. If you have used identical commands before, you can find your past commands by simply using the *up* and *down* buttons. 

> For example,
> ```bash
> # Let's say we used the following commands in order
>
> cd Desktop/
> ls
> cd ..
> 
> # Let's say we want to use cd Desktop/ again
> # We can press up three times to the third recent command, which is cd Desktop/
> 
> cd Dekstop/
> 
> # Let's say we want to use ls instead
> # We can press down one time to the second recent command, which is ls
>
>ls
> ```
>Try it on your own!


2. If the past commands was too long ago, you can search for it using the command *ctrl-r* to open the backward in history (bck-i-search) tool.
   
> ![](ctrl-r1.png)
>
> Start to enter the command you want to write, the search will help you find it from your bash history. Let's say we want to find our *ssh* command to the remote server.
>
> ![](ctrl-r2.png)
> 
> Here, I entered *ssh* and the terminal helped me find my intended command that I used in the past. If you can't find the command, you can try to use *ctrl-r* again or provide more information about your intended command.

### Use a Script

You can also write a bash script to run your commonly used command combos.

1. First, you can create an *.sh* file on your local computer using VSCode or terminal. 
2. Put #!/bin/bash in your first line. 
3. Next, type your commands in the following lines. 
4. At last, when you need to use the script, call it in the terminal by:
  ```bash
  sh <script_file> [$1] [$2] ... [arguments]
  ```

> Example 1: Connect to the remote server
>
> It can always be quite annoying to type your username every single time you want to log in to the remote server.
>
> ssh_15l.sh
> ```bash
> #!/bin/bash
> 
> ssh username@ieng6.ucsd.edu
> ```
> Now, we can run this program in the terminal:
> 
> ![](sh_ex1.png)

> Example 2: Send files to the remote server
>
> Similar to the first example, the *scp* commands can be quite long.
>
> scp_15l.sh
> ```bash
> #!/bin/bash
>
> # SOURCE=$1
> # DESTINATION=$2
>
> scp $1 cs15lfa22lb@ieng6.ucsd.edu:$2
> ```
> Now, we can run this program in the terminal. Also, *$x* means the *x*-th parameter.
>
> ![](sh_ex2.png)
>
> Here, WhereAmI.java in Desktop is copied to the current/default (.) directory in the remote server.

Although I am only running one command in my script, you can have multiple command run at once. It can sure save a lot of time from running common long commands everytime. You should definitely learn and play with it on your own! 

***

***Good Job! You have reached the end of the tutorial to run remote server. See you next time!***