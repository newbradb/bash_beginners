## 1.7. Exercises

### 1. Where is the bash program located on your system?

```console
$ which bash
/bin/bash
```

### 2. Use the --version option to find out which version you are running.

```console
$ bash --version | head -1 | awk '{print$4}'
4.4.20(1)-release
```

### 3. Which shell configuration files are read when you login to your system using the graphical user interface and then opening a terminal window?

When you login in GUI you don't get shell, instead you get session manager or window manager.

The following file read because you are opening non-login interactive shell :

```
~/.bashrc
```

### 4.  Are the following shells interactive shells? Are they login shells?

*Interactive means you can enter commands.  
Login shell means that you got the shell after authenticating to the system, usually by giving your user name and password.*

[Good explanation with examples](https://unix.stackexchange.com/questions/38175/difference-between-login-shell-and-non-login-shell)

-A shell opened by clicking on the background of your graphical desktop, selecting "Terminal" or such from a menu.

Interactive, non-login

-A shell that you get after issuing the command ssh localhost.

Interactive, login

-A shell that you get when logging in to the console in text mode.

Interactive, login

-A shell obtained by the command xterm &.

Interactive, non-login

-A shell opened by the mysystem.sh script.

Non-interactive, non-login

-A shell that you get on a remote host, for which you didn't have to give the login and/or password because you use SSH and maybe SSH keys.

Interactive, login

### 5. Can you explain why bash does not exit when you type Ctrl+C on the command line?

Ctrl+C is the interrupt signal. Terminal window is interactive shell not the process.

### 6. Display directory stack content  

The directory stack is a list of directories you have previously navigated to.

```console
~$ echo $DIRSTACK
~
```
[Working with the directory stack in linux](https://www.putorius.net/pushd-popd-linux.html)

### 7. If it is not yet the case, set your prompt so that it displays your location in the file system hierarchy, for instance add this line to ~/.bashrc:

```
export PS1="\u@\h \w> "
```
### 8. Display hashed commands for your current shell session.

```console
$ hash
hits	command
   1	/usr/bin/vim
   1	/usr/bin/w
   3	/bin/ls
```


