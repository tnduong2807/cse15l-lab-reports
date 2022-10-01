# Week 1 Lab Report
Hello, this topic will be remore access and filesystem. Follow each step to complete remote access tutorial!
## Step 1: Installing VScode
Use this link [https://code.visualstudio.com/](https://code.visualstudio.com/) to go to the Visual Studio Code website, and follow the instructions of the website to download and install vscode on your computer (**Be carefull for different major operating systems such as OSX(for Macs) and Windows (for PCs)**). If you encounter an error installing Visual Studio Code, please speak to your tutor or ask your groupmates for help.
When you completed installing VScode, open it and you should see a window of Vscode look like this (depend on your system and settings, your window could look a bit different):
![](https://github.com/tnduong2807/cse15l-lab-reports/blob/main/Screenshot%20(14).png?raw=true)

## Step 2: Remotely Connecting
* Follow the intructions and only install OpenSSh **client**, not the server:
[**Install OpenSSH**](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
* For reference, you could use this link and follow the instructions in [**"Connect to a remote host"**](https://code.visualstudio.com/docs/remote/ssh#_connect-to-a-remote-host).
* First step, open a terminal in VSCode (Ctrl or Command + `, or press Terminal then New Terminal option on the menu bar). You should enter the command in the Terminal look like this but replace **by** with the letter in your course-specific account.
`$ ssh cs15lfa22by@ieng6.ucsd.edu`
* You will probably get a message like this because this is likely the first time you've connected to this server.
```
⤇ ssh cs15lfa22by@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```
* It mean that someone is trying to control the connection and ask you for permission. So please type **yes** and press enter, then the Terminal interaction should look like this and please enter your **password**:
```
# On your client
⤇ ssh cs15lfa22by@ieng6.ucsd.edu
The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
Password: 
```
* Now your terminal is connected to a computer in CSE basement and your Terminal should show this output:
```
Last login: Mon Apr  4 09:54:02 2022 from its-cseb260-40.ucsd.edu

Hello cs15lfa22by, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status
Hostname     Time    #Users  Load  Averages
ieng6-201   17:00:01   20  0.43,  0.17,  0.10
ieng6-202   17:00:01   15  0.14,  0.12,  0.13
ieng6-203   17:00:01   18  0.01,  0.07,  0.06


Wed Sep 28, 2022  5:02pm - Prepping cs15lfa22
```
* If you run into some errors and can't connected to the server, please ask for help!

## Step 3: Trying Some Commands
Now trying to run commands such as **cd**, **ls**, **pwd**, **mkdir**, and **cp** on your computer and on the connected remote computer after connected remote access.
There are some useful commands to try running:
* cd ~
* cd
* ls -lat
* ls -a
* ls <directory> and replace <directory> with /home/linux/ieng6/cs15lfa22/cs15lfa22**by**, and change **by** to one of your groupmate's username.
* cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/
* cat /home/linux/ieng6/cs15lfa22/public/hello.txt
**To log out of the remote server on your terminal, you can use:**
* Ctrl-D
* Type the command **exit** and press enter
Here are the examples when you ran the commands:
![](https://github.com/tnduong2807/cse15l-lab-reports/blob/main/Screenshot%20(22).png?raw=true)

## Step 4: Moving Files with **scp**
In this step, you learn how to copy files back and forth between the computer on the server. Use the Command **scp** on your client Terminal (not connected to **ieng6**). Create a file called **WhereAmI.java** on your computer and enter the following contents into it:
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
Use the comands **javac** and **java** on your Terminal to compile and run the WhereAmI.java file like below.
```
javac WhereAmI.java
java WhereAmI
```
**Skip this step if you didn't install **java** on your computer.**
In your terminal, run this command and replace **cs15lfa22by** with your username:
`scp WhereAmI.java cs15lfa22by@ieng6.ucsd.edu:~/`
It will require you to enter your password just like when you log in the server with **ssh**. If you run into errors, please ask your help.
Now log into ieng6 with **ssh**, and use the command **ls** (You should see the file there in your home directory on your Terminal!). You can run the **WhereAmI** program on the **ieng6** computer using the commands **javac** and **java** from above because **java** is installed on the server ieng6.
```
javac WhereAmI.java
java WhereAmI
```
After you run the program, you Terminal should look like this:
![](https://github.com/tnduong2807/cse15l-lab-reports/blob/main/Screenshot%20(17).png?raw=true)

## Step 5: Setting an SSH Key
* Now you could save up a lot of times by setting up an SSH Key because you won't have to enter your password when log in or copy files to a remote server with **ssh** and **scp**.
* Run the command **ssh-keygen** on your terminal to create a pair of files that called the *public* key and *private* key
* You will copy and put the public key to a specific location on the server, and private key in a other specific location on the client.
* Then the **ssh** command can use the pair of files rather than your password.
* Your Terminal should look like this, you can press **enter** to stay as the default path when the prompt **Enter file in which to save the key (/Users/duong/.ssh/id_rsa):** show up.
```
(on the terminal of your computer **not connect to the server**)
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/joe/.ssh/id_rsa.
Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+
```
If you are on Windows, and have some problem with the **ssh-keygen** command, please follow the extra **ssh-add** steps in this link or ask for help:
[https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

* Now two new files created on your system, the file **id_rsa** as the private key and the file **id_rsa.pub** as the public key stored in the **.shh** directory on your computer.
* You need to copy the public key or the file **id_rsa.pub** to the **.ssh** directory of your user account on the server, enter the command:
```
(On your computer terminal **not connected to the sever**)
$ ssh cs15lfa22zz@ieng6.ucsd.edu
<Enter Password to log in your server>
```
```
(Now on your server terminal)
$ mkdir .ssh
$ <use command **exit** to logout>
```
```
(Back to your computer terminal)
$ scp /Users/duong/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys
(Please use your username and the path you saw or set up in the command above)
```
When you did this, you won't have to enter your password when your run **ssh** and **scp** from your client to the server.

## Step 6: Optimizing Remote Running
Now you could make remote running more efficient by using shortcut or other features, try to get total times for a run after editing and saving to under 10 total keystrokes or click buttons/mouse.
Here is some command could help you:
* You can use command **ssh** in quotes at the end to directly run it on the remote server:
`$ ssh cs15lfa22@ieng6.ucsd.edu "ls"`
* You can run multiple commands on the same line by separate them with semicolons in most terminals:
`$ cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`
* You can use the up-arrow on your keyboard to recall the commands that was run.
Here is an example output when you run those commands:
![](https://github.com/tnduong2807/cse15l-lab-reports/blob/main/Screenshot%20(25).png?raw=true)

**Congratulation you have completed the tutorial of remote access!**
