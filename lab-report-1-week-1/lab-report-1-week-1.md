# Week 1: Lab Report 1
*By Kevin Chan, September 30, 2022*

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
    - [Exit (*exit or Ctrl-d*)](#exit-exit-or-ctrl-d)
  - [Moving Files with *scp*](#moving-files-with-scp)
  - [Setting an SSH Key](#setting-an-ssh-key)
  - [Optimze Remote Running](#optimze-remote-running)
    - [Using Tab](#using-tab)
    - [Using a Script](#using-a-script)

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

Congrats! You successfully connected to the UCSD Remote Server. If your password isn't working, maybe the server hasn't been updated with your new password yet.

***

## Some Commands You Can Try

It is very important to know your terminal commands! Here are some you can try!

### Print Working Directory (*pwd*)

```bash
pwd
#returns the current working directory 
```
![](pwd.png)

### List (*ls*)

```bash
ls
#returns the visible files in your directory

ls -a
#returns both the visible and hidden files in your directory
```
![](ls.png)
### Change Directory (*cd*)

```bash
cd [directory]
#change to your intended directory

cd ..
#returns to the parent directory
```

![](cd.png)

### Make/Remove Directory (*mkdir / rmdir*)

```bash
mkdir <directory>
#creates your intended directory

rmdir <directory>
#removes your intended directory
```

![](mkdir.png)
### Create File (*touch*)

```bash
touch <file>
#creates your intended file
```

### Remove File (*rm*)

```bash
rm <file>
#removes your intended file
```

### Concatenate (*cat*)

```bash
cat <file> ... [more files]
#previous your intended file
```

### Copy (*cp*)

```bash
cp <folder/file> <destination>
#previous your intended file
```

### Exit (*exit or Ctrl-d*)

```bash
exit
or Ctrl-d
#exits remote server
```

***

## Moving Files with *scp*


***

## Setting an SSH Key

***

## Optimze Remote Running
### Using Tab

### Using a Script