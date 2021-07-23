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
      - $echo $PATH



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



