# Linux 

***Linux Commands, Configurations and the Internals.***
<br />

***This is to display about the linux commands, configurations, and the internals in it.***
<br />

***The Author used Ubuntu 20.04 for this exercise and the O/S ran on the Hypervisor VMware Worstation 15 player.***
<br />

- sudo iptables -L

- nmap -PO ipaddress

- netstat -apnn | grep LISTEN | egrep ‘993|143’

- netstat -apnn | grep LISTEN | egrep '993|143' - https://serverfault.com/questions/317860/how-do-i-find-out-if-my-server-is-running-imap/317869


## An introduction of how Linux works

**Linux is based on the UNIX Operating System, and it was built in the year 1991. Its name Linux is consented and dedicated to its founder Linux Torvalds.** 

### So at first let's take  look at how UNIX funtions (the precursor) and move onto linux along the way.

**Unix users could direct an output of a command using the right arrow key (>). But then later the concept was added where the output of a command could be directed to the input of another component. For example the following command line term concaenates (cat) file 1, file 2, sorts (sort) the lines in those files alphabetically, paginates the sorted text for printing (pr), and directs the output to the computers default printer (lpr)**

$ cat file 1 | file 2 | sort | pr | lpr 




## Important ports to take care when learning about linux

- LDAP belongs to port 389

## Cool Shortcuts when using linux with the praphical interface, GNOME.

- Ctrl + Alt + Tab - To open the windows (Add the Fn key when opening these using VMware Workstation 15 player)
- Alt + ` (backtrace, which is on top of the tab key) - This shows opened windows, and the user can select the one which they wish to open by selecting the window using the computer mouse.
- Alt + F2 - To display a command box (Alt+Fn+F2 - When using the VMware Workstation 15 player).
- Ctrl + D + Super Key (the windows key) - When there are windows opened on the desktop, using these key combination would allow to view the desktop.
- sudo nautilus - Opens the file explorer with root permissions in it.
- top - Type this on the command line to see the running processors. To quit this activity press the letter 'q'. The top command outputs an activity similar to something of the windows task manager in Microsoft Windows.
- Alt + Shift + Esc - Cycle backward without pop-up icons.
- Alt + Ctrl  + Shift + Tab - Cycle backward among panels.
- Esc - Close Menu.
- Alt + F2 => To type a program to open such as "gedit".
- Ctrl + Alt + L - Lock Screen.
- Alt + F1 - Shows the main menu (Add the 'Fn' key in between when using the VMware Workstation 15 player).
- Alt + PrintScreen - Print the entire desktop (Add the 'Fn' key in between when using VMware Workstation 15 player).
- gconf-editor - To view and change information about some control (This will have to be installed at first by typing "sudo apt install gconf-editor"). 


## How to use the Linux Shell

- The shell is represented by the "sh" command.

<br />

- Ubuntu uses the dash shell, by default, which is designed to perform faster than the bash shell. Linux also has a tcsh shell (an improved C shell) and an ash shell (another Bourne shell look-alike).

<br />

- $ - The default prompt for a regular user is shown by a dollar sign.

<br />

- The pound sign (#) is Tthe default prompt for the root user, this is also called as the hash mark.

<br />

- A login prompt for a user named jibs on the computer named ubuntu with /usr/share/ as the current working directory would appear as:

- [jibs@ubuntu share] $

<br />

- gnome-terminal – Type this to open a new terminal


- To open the virtual consoles use the key strokes Ctrl + Alt + F1 (or F2, F3, F4, F5, and so on up to f6 on most Linux systems) - (Add the ‘Fn’ key in between when using the VMware Workstation 15 player)


<br />


- Type “exit” to exit from the shell.

<br />

- To find out what your default shell is, type the following:
                                      *  whoami – Shows your username.
                                      *  grep /chris/etc/passwd – Replacing Chris with your name shows the definition of your account in the /etc/passwd/ file.
                                 
- date – To display the date.
- pwd – To print the working directory or the place in the folder where the user is in.
- hostname – Shows the computers hostname.
- ls – Lists all the files and the directories in your current directory.
- more – To type after the command to modify its behaviour.

<br />

***The characters and words you can type after a command are called options and arguments.***

<br />

- ls -l -a -t
- ls -lat
In both cases, the ls command runs with the -l (long listings), -a (shows the hidden dot files), and -t (lists by time) options.

***To tell a command to use a whole word as an option, you typically precede it with a double hyphen (- -)  for example the “- - help” command.***

***Ex: hostname - - help***

<br />

- cat /etc/passwd
  - cat is the command.
  - /etc/passwd – is the argument.

- For full-word options, the argument often follows an equal sign (=). Here is an example:

  - eg: ls - - hide=Desktop

  - In this example, the - - hide option tells the ls command to not display the file or directory named Desktop when listing the contents of the directory.

<br />

- tar - cvf backup.tar /home/chris

  - c – create
  - v – verbose
  - f – file 

  - named backup.tar 

  - /home/chris – This includes all the contents of the /home/chris directory and its sub directories and shows verbose messages as the backup is created.

<br />

- ls -a = To see the hidden files in the directory (the files that begin with the dot).
- uname -m = The type of system you are running (Linux).
- uname -a =  With -a, the hostname, kernel release, and kernel version can also be seen.
- date +’%d/%m/%y’
- id = User id
- who = Who is logged in

<br />

***Linux distributions that have Security Enhanced Linux (SELinux) enabled, such as Fedora and RHEL, show additional information at the end of the id output. The output might look something like the following:***

***context=unconfined_u:unconfined_r:unconfined_t :s0-s0:c0.c1023***

<br />

- who -uH

  - who = current login session
  - -u = information about the idle time and the process id
  - H = Header to be printed

<br />

***You can run the “date” command from the  /bin directory by typing: $ /bin/date***

<br />

- To see you current path: echo $PATH

***Most user commands that come with Linux are stored in /bin, /usr/bin, or /usr/local/bin directories. The /sbin and the /usr/sbin directories contain administrative commands.***

<br />

- The command **"who -uH"** would show the name of the remote computer the user has logged in from, if that user had logged in from another computer on the network, or the name of the local X display, if that user were using a Terminal window (such as O:O).

<br />

- Locating Commands – One way is to run the command by using the absolute path. 
  - Eg: - To run the “date” command from the /bin directory by typing: $ /bin/date.

  - This can be inconvenient especially if the command resided in a directory with a long path name. The better way is to have the commands stored in well known directories and then add these directories to your shells PATH environment variable. The path consists of a list of directories that are checked sequentially for the commands you enter. 
    - To see your current path, type the following:
      $echo $PATH

- **Tip:** If you want to add your own commands or shell scripts, place them in the “bin” directory in your home directory (such as /home/chris/bin for the user named Chris). This directory is automatically added to your path in some Linux systems, although you need to create that directory or add it to your PATH on other Linux systems. So, as long as you add the command to your bin with execute permission, you can begin using it by simply typing the command name at your shell prompt. To make commands available to all users, add them to the /usr/local/bin.

<br />

- Directories are checked from left to right. Eg: /bin and /usr/bin is a file in /bin where it gets executed.

<br />

- Alias – “alias” is a command that represents a particular command and a set of options. Often, aliases enable you to define a short name for a long, complicated command. Typing the ‘alias’ command will show the commands that have an alias for it.

<br />


- cd – To change directories.
- echo – To output text to the screen
- exit – To exit from a shell.
- fg – To bring a command running in the background to the foreground.
- history – To see a list of commands that were previously run.
- pwd – To represent the present working directory.
- set – To set shell options.
- type – To show the location of a command. To find out where a particular command is taken from. (If you are using a shell other than bash, use the which command instead:
  - $ type bash

<br />

- bash is /bin/bash.

<br />

- type which, type case, and type return. The command type -a ls should show aliased and filesystem location for command "ls".

<br />

- Command not found may not be in the located path variable.

<br />

- Permisison denied = The command may be in the PATH variable, but may not be executable.

<br />

- If a command is not in your PATH variable, you can see the “locate” command. Eg: “locate chage”. -  - The locate command looks all over your filesystem, not just in directories that contain commands. This needs to be installed.

<br />

- “find” is the same as locate, however locate works more efficiently. It uses one or more databases populated by updatedb program and prints filenames making at least one of the pathnames (a user provides) to standard output.

<br />

- The locate package is provided by the GNU Findutils or mlocate package. The “mlocate” package which provides the locate and updatedb commands to find the files in Linux systems.

<br />

- locate bash_completion.sh
- rpm -qa | grep findutils

<br />

- ***By default, the bash shell uses command-line editing that is based on the emacs text editor. (Type*** **man emacs** ***to read about it, if you care to.) If you are familiar with emacs, you probably already know most of the keystrokes described here.
  - **Tip**
  <br />
  If you prefer the **vi** command for editing shell command lines, you can easily make that happen. Add the following line to the **.bashrc** file in your home directory:
  - set -o vi
 The next time you open a shell, you can use vi commands to edit your command lines.
 
- Emacs editor - 

<br />

- **To try out a bit of command-line editing, type the following:**
    - $ ls /usr/bin | sort -f | less
      > This command lists the contents of the /usr/bin directory, sorts the contents in alphabetical order (regardless of the case), and pipes the output to less. The less command displays the first page of the output, after which you can go through the rest of the output from a line (by pressing the Enter key) or a page (press the spacebar key) at a time. Simply press q when you have finished. 


### Keystrokes for navigating through the command line

| Keystroke | Full Name         | Meaning |
| --------- | ----------------- | ------- |
| Ctrl+F    | Character Forward | Goes one character forward.   |
| Ctrl+B    | Character Backward| Goes one character backwards. |
| Alt+F | Word Forward| Go one word forward. |
| Alt+B | Word Backward | Go one word backwards. |
| Ctrl+A | Beginning of the line | Go to the beginning of the current line. |
| Ctrl+E | End of the line | Go to the end of the line. |
| Ctrl+L| Clear the screen | Clear the screen and leave the line at the top of the screen |

<br />

### Keystrokes for Editing the Command Line

| Keystroke | Full Name | Meaning |
| --------- | --------- | ------- |
| Ctrl + D | Delete Current | Delete the current character. |
| Backspace| Delete the previous | Delete the previous character. |
| Ctrl+T | Transpose character | Switch positions of the current and previous words. |
| Alt+T | Transpose Words | Switch positions of the current and the previous words. |
| Alt+U | Uppercase Word | Change the current word to the uppercase of it. |
| Alt+L | Lowercase Word | Chage the current word to the lowercase of it. |
| Alt+C| Capialize Word | Chnage the current word to an initial capital. |
| Ctrl+V | Insert a sppecial character | Add a special character. For example, to add a Tab character, press Ctrl+V+Tab |

<br />

### Keystrokes for Cutting and Pasting Text from within Command Lines

| Keystroke | Full Name | Meaning |
| --------- | --------- | ------- |
| Ctrl+K | Cut end of line | Cut text to the end of the line. |
| Ctrl+U | Cut beginning of line | Cut text to the beginning of the line. |
| Ctrl+W | Cut previous word | Cut the word located behind the cursor. |
| Alt+D | Cut next word | Cut the word following the cursor. |
| Ctrl+Y | Paste recent text | Paste most recently cut text. |
| Alt+Y | Paste earlier text | Rotate back to previously cut text and paste it. |
| Ctrl+C | Delete whole line | Delete the entire line. |

<br />

  - **Command-line completion**
    > To save you a few keystrokes, the bash shell offers several different ways of completing partially typed values. To attempt to complete a value, type the first few characters and press Tab. Here are some of the values you type partially from a bash shell:

      - **Command, alias, or function -** If the text you type begins with regular characters, the shell tries to complete the text with a command, alias, or function name.
      -  **Variable -** If the text you type begins with a dollar sign ($), the shell completes the text with a variable from the current shell.
      -  **Username -** If the text you type begins with a tilde (~), the shell completes the text with a username. As a result, ~username indicates the home directory of the named user.
      -  **Hostname -** If the text you type begins with the at symbol (@), the shell completes the text with a hostname taken from the /etc/hosts file.
      
    - **Tip** - To add hostnames from an additional file, you can set the HOSTFILE variable to the name of that file. The file must be in the same format as /etc/hosts.


  - Here are a few examples of command completion. (When you see <Tab>, it means to press the Tab key on your keyboard.) Type the following:
    - echo $OS<Tab>
    - cd  ~ro<Tab>
    - fing<Tab>
  
  - The first example causes $OS to expand to the $OSTYPE variable. In the next example, ~ro expands to the root user's home directory (~root/). Next, fing expands to the finger command.
  
  - Pressing the Tab key twice offers some wonderful posisbilities. Sometimes, several posisble completions for the string of characters you have entered are available. In those cases, you can check the possible ways text can be expanded by presisng Tab twice at the point where you want to do completion.
  
  - The following shows the result you would get of you checked for possible completions on $P:
  
    - $ **echo $P<Tab><Tab> **
    - $ PATH $PPID  $PS1  $PS2  $PS4  $PWD
    - $ echo $P
  
  - In this case, there are six possible variables that begin with $P. After the possibilities are dispalyed, the original command line returns, ready for you to complete it as you choose. For example, if you typed another P and pressed Tab again, the command line would be completed with $PPID (the only unique posisbility).
  
  ### Few commands to learn
  
  - history > history_for_print.txt – All the command history will be pushed to a new file called history_for_print.txt.





******
******
******
******
******
******
******
******
******
******
******
******
******
******
******
******
******
******



