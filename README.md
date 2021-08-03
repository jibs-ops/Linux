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

    - Example: $ alias mv
                 alias mv='mv -i' 

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
  
  <br />
  
  ### Few commands to learn here.
  
  - history > history_for_print.txt – All the command history will be pushed to a new file called history_for_print.txt.
  - !n – Run the command number. Replace n with the number in the command line.
  - !! - run the previous command.
  - !?string? — Run a command that contains a string. This runs the most recent command that contains a particular string of characters. For example, you can run the date command again by just searching for part of that command line as follows:

    - $ !?
      - Output - dat?dateWed Oct 29 21:32:41 PDT 2014 
  

<br />
  
| Key(s)  | Function Name | Description |
| ------  | ------------- | ----------- |
| Arrow Keys (up and down)  | Step  | Press the up and down arrow keys to step through each command line in your history list to arrive at the one you want. (Ctrl+P and Ctrl+N do the same functions, respectively.) |
| Ctrl+R  | Reverse incremental search  | After you press these keys, you enter a search string to do a reverse search. As you type the string, a matching command line appears that you can run or edit. |
| Ctrl+S  | Forward incremental search  | This is the same as the preceeding function but for forward search. (It may not work in all instances.)|
| Alt+P | Reverse search  | After you press these keys, you enter a string to do a reverse search. Type a string and press Enter to see the most recent command line that includes that string. |
| Alt+N | Forward search  | This is the same as the preceeding function but for forward search. (It may not work in all instances.) |
  
  
 -  Another way to work with your history list is use the fc command. Type **fc** by a history line number, and that command line is opened in a text editor (vi by default; type **:wq** to save and exit or **:q!** to just exit if you are stuck in vi). Make the changes that you want. When you exit the editor, the command runs. You can also give a range of line numbers (for example, fc 100 105). All the commands you open in your text editor, and then run one after the other when you exit the editor.
  
  - After you close your shell, the history list is stored in the .bash_history file in your home directory. Up to 1,000 history commands are stored for you by default.
  
  - **Note -**
    > Some people disable the history feature for the root user by setting the HISTFILE to /dev/null or simply leaving HISTSIZE blank. This prevents information about the root user's activities from potentially being exploited. If you are an administrative user with root privileges, you may want to consider emptying your file upon exiting as well for the same reasons. Also, because shell history is stored permanently when the shell exits properly, you can prevent storing a shell's history by killing a shell. For example, to kill a shell with process ID 1234, type kil -9 1234 from any shell.
  
- A metacharacter is a typed character that has a special meaning to the shell for connecting commands or requesting expansion. Metacharacters include the pipe character (|), ampersand (&), semicolon (;), right parenthesis ( ) ), left parenthesis ( ( ), less than sign (<), and greater than sign (>). 
 
 -  In UNIX to see how the document really appeared, they would use a command such as the following:
    - $ gunzip < /usr/share/man/man1/grep.1.gz | nroff -c -man | less 
                                              
 
  > In this example, the contents of the grep man page (grep.1.gz) are directed to the gunzip command to be unzipped. The output from gunzip is piped to the nroff command to format the man page using the manual macros (- man). The output is piped to the less command to display the output. Because the file being displayed is in plain text, you could have substituted any number of options to work with the text before displaying it. You could sort the contents, change or delete some of the content, or bring in text from other documents. The key is that, instead of all those features being in one program, you get results from piping and redirecting input and output between multiple commands. 
  
<br />
  
### Sequesntial Commands
  
- Sometimes, it may be needed that a sequence of commands will have to be executed, with one command completing before the next command begins. You can do this by typing several commands on the same command line and separating them with semicolons (;):
    - $ date  ; troff -me verylargedocument | lpr ; date
  
  > In the above example, I was formatting a huge document and wanted to know how long it would take. The first comman (date) showed the date and tim before the formatting started. The "troff" command formatted the document and then piped the output to the printer. When the formatting was finished, the date and time were printed again (so I knew how long the "troff" command took to complete).
  
- Another useful command to add to the end of a long command line email. You could add the following to the end of a command line.
  
  - ; mail  -s  "Finished the long  command"  chris@example.com
  
- Then, for example,  a mail message is sent to the user you choose after the command completes.

- You can have the commands run in the background by using the ambersand (&).
  
- On Unix-like operating systems, the nroff command (short for "new runoff"), is used to format ("run off") documents for display or fixed-width printing. In addition to user functions, internally, the system uses it to format the text in man pages.
  
- On Unix-like operating systems, the troff command performs typesetting functions and formats documents. It is the major component of the document processing system developed by AT&T for Unix.
  
### Background commands
  
- Some commands can take a while to complete. Sometimes, you may not want to tie up your shell waiting for a command to finish. In those cases, you can have the commands run in the background by using the ampersand (&).
  
- Text formatting commands (such as "nroff" and "troff", described earlier) are examples of commands that are often run in the background to format a large document. You also might want to create you own shell scripts that run in the background to check continuously for certain events to occur, such as the hard disk filling up or particular users loggin in.
  
- The following is an example of a command being run in the background:
   -  $ troff -me verylargedocument | lpr &
  
- Don't close the shell until the process is completed, or that kills the process.
  
- The two forms of command substitution are $(command) and `command` (backticks, not single quotes). 
  
### Expanding commands
  
- With command substitution, you can have the output of a command interpreted by the shell instead of by the command itself. In this way, you can have the standard output of a command become an argument for another command. The two forms of command substitutions are $(command) and `command` (backticks, not single quotes).
  
- The command in this case can include options, metacharacters, and arguments. The following is an example of using command substitution:
  
  - $ vi $(find /home | grep xyzzy)

- In this example, the command substitution is done before the vi command is run. First, the find command starts at the /home directory and prints out all files and directories below that point in the filesystem. The output is piped to the grep command, which filters out all files except for those that include the string xyzzy in the filename. Finally, the vi command opens all filenames for editing (one at a time) that include xyzzy. (If you run this and are not familiar with vi, you can type :q! to exit the file.)
  
- This particular example is useful if you want to edit a file for which you know the name but not the location. As long as the string is uncommon, you can find and open every instance of a filename existing beneath a point you choose in the filesystem. (In other words, don’t use grep from the root filesystem or you’ll match and try to edit several thousand files.)
  
### Expanding arithmetic operations
  
- There are two forms you can use to expand an arithmetic expression and pass it to the shell: 
  - $[expression] or $(expression). 
  
- The following is an example:

- $ echo "I am $[2015 - 1957] years old."
  - I am 58 years old.

- The shell interprets the arithmetic expression first (2015 - 1957) and then passes that information to the echo command. The echo command displays the text, with the results of the arithmetic (58) inserted. 

- Here’s an example of the other form:

- $ echo "There are $(ls | wc -w) files in this directory."
  - There are 14 files in this directory.

- This lists the contents of the current directory (ls) and runs the word count command to count the number of files found (wc -w). The resulting number (14, in this case) is echoed back with the rest of the sentence shown. 
  
### Expanding variables

- Variables that store information within the shell can be expanded using the dollar sign ($) metacharacter. When you expand an environment variable on a command line, the value of the variable is printed instead of the variable name itself, as follows: 

- ls -l $BASH
  - -rwxr-xr-x 1 root root 1012808 Oct 8 08:53 /bin/bash 

- Using $BASH as an argument to ls -l causes a long listing of the bash command to be printed. 
  
  
### Using Shell Variables 
 
- Examples of variables include $SHELL (which identifies the shell you are using), $PS1 (which defines your shell prompt), and $MAIL (which identifies the location of your mailbox).

- You can see all variables set for your current shell by typing the set command. A subset of your local variables are referred to as environment variables. Environment variables are variables that are exported to any new shells opened from the current shell. Type env to see environment variables.

- You can type echo $VALUE, where VALUE is replaced by the name of a particular environment variable you want to list. And because there are always multiple ways to do anything in Linux, you can also type declare to get a list of the current environment variables and their values along with a list of shell functions. 

  - $ echo $USER
    - chris

  - This command prints the value of the USER variable, which holds your username (chris). 
  
| Variable  | Description |
| --------  | ----------- |
| PROMPT_COMMAND  | This can be set to a command name that is run each time before your shell prompt is diplayed. Setting PROMPT_COMMAND=date lists the current date/time before the prompt appears.  |
| PS1 | This sets the value of your shell prompt. There are many items that you can read into your prompt (date, time, username, hostname, and so on). Sometimes a command requires additional prompts, which you can set with the variales PS2, PS3, and so on.  |
| PWD | This is the directory that is assigned as your current directory. This value changes each time you change directories using the cd command. |
| RANDOM  | Accessing the variable causes a random number to be generated. The number is between 0 and 99999. |
| Seconds  | This is the numbe rof seconds since the time the shell was started. |
| SHLVL | This is the number of shell levels associated with the current shell session. When you log to the shell, the SHLVL is 1. Each time you start a new bash command (by, for exmaple, using su to become a ne wuser, or by simply typing bash), this number is incremented. |
| TMOUT | This can be set to a number representing the numbe rof seconds the shell can eb idle without receiving input. After the number of seconds is reached, the shell exits. The security feature makes it less likely for unattended shells to be accessed by unauthorized people. (This must be set in the login shell for it to actually cause the shell to log out the user.) |
  
  
### Creating and using aliases

- Using the alias command, you can effectively create a shortcut to any command and options you want to run later. You can add and list aliases with the alias command. Consider the following examples of using alias from a bash shell:

  - $ alias p='pwd ; ls –CF'
  - $ alias rm='rm -i'

- In the first example, the letter p is assigned to run the command pwd, and then to run ls -CF to print the current working directory and list its contents in column form. The second example runs the rm command with the -i option each time you type rm. (This is an alias that is often set automatically for the root user. Instead of just removing files, you are prompted for each individual file removal. This prevents you from automatically removing all the files in a directory by mistakenly typing something such as rm *.) 

- You can check which aliases are set by typing the alias command. If you want to remove an alias, type unalias. (Remember that if the alias is set in a configuration file, it will be set again when you open another shell.)
  
-  To exit the shell when you are finished, type exit or press Ctrl+D. 

-  The su command opens a shell as a new user. 
  
  
### Confugring your shell
  
- Several configuration files support how your shell behaves. Some of the files are executed for every user and every shee, whereas others are specific to the user who creates the configuration file. The tabl below shows the files that are of interest to anyone using the bash shell in Linux. (Notice the use of ~ in the filenames to indicate the the file is located in each user's home directory.)
  
### Bash Configuration Files

| File  | Description |
| ----  | ----------- |
| /etc/profile  | This sets up user environment information for every user. It is executed when you first log in. This files provides values for you path, in addition to setting environment variables for such things as the location of your mailbox and the size of your history files. Finally, /etc/profile gathers shell settings from configuration files in the /etc/profile.d directory.  |
| /etc/bashrc | This executes for every user who runs the bash shell, each time a bash shell is opened. It sets the default prompt and may add one or more aliases. Values in this file can be overridden by information in each user's ~/.bashrc file. |
| ~/.bash_profile | This is used by each to enter information that is specific to his or her use of the shell. It is executed only once, when the user logs in. By default, it sets a few environment variables and executes the user's .bashrc file. This is a good place to add environment variables because, once set, they are inherited by future shells. |
| ~/.bashrc | This contains the information that is specific to your bash shells. It is read when you log in and also each time you open a new bash shell. This si the best location to add aliases so that your shell picks them up. |
| ~/.bash_logout  | This executes each time you log out (exit the last bash shell). By default, it simply clear your screen.  |
  
- To change the /etc/profile or /etc/bashrc files, you must be the root user. Users can change the information in the $HOME/.bash_profile, $HOME/.bashrc, and $HOME/.bash_logout files in their own home direcotries.
  
- type nano $HOME/.bashrc
  > In the nano editor type: alias d='date +%D' . Open a new shell and just type d.

- To have the new information you just added to the file available from the current shell, type the following:

  - $ source $HOME/.bashrc 

- If you change directories, the bin name would change to the name of the new directory. 


Characters to Add Information to bash Prompt
  
| Special Character | Description |
| ----------------- | ----------- |
| \!  | This shows the current command history number. This includes all previous commands stored for your username.  |
| \#  | This shows the command number of the current command. This included only the commands for the active shell. |
| \$  | This shows the user prompt ($) or root prompt (#), depending on which user you are. |
| \W  | This shows only the current working directory's base name. For example, if the current working directory was /var/spool/mail, this value simply appears as mail.  |
| \[ | This precedes a sequence of nonprinting characters. This can be used to add a terminal control sequence into the prompt for such things as changing colours, adding blink effects, or making characters bold. (Your terminal determines the exact sequences available.)
| \] | This follows a sequence of nonprinting characters.  |
| \\  | This shows a backslash. |
| \d  | This displays the day name, month, and day number of te current date - for example, Sat Jan 23. |
| \h  | This shows the hostname of the computer running the shell.  |
| \n  | This causes a newline to occur. |
| \nnn  | This shows the character that relates to the octal number replacing nnn.  |
| \s  | This displays the current shell name. For the bash shell, the value would be bash.  |
| \t  | This prints the current time in hours, minutes, and seconds - for example, 10:14:39 |
| \u  | This prints your current username.  |
| \w  | This displays the full path to the current working directory. |
  
- To make a change to your prompt permanent, add the value of PS1 to your .bashrc file in your home directory (assuming that you are using the bash shell). There may already be a PS1 value in that file that you can modify. Refer to the Bash Prompt HOWTO (http://www.tldp.org/HOWTO/Bash-Prompt-HOWTO) for information on changing colors, commands, and other features of your bash shell prompt. 

<br />
  
### Adding environment variables

- You might want to consider a few environment variables to your .bashrc file. These can help make working with the shell more efficient and effective:
  
  - TMOUT - This sets how long the shell can be inactive before bash automatically exists. The value is the number of seconds for which the shell has not received input. This can be a nice security feature, in case you leave your desk while you are still logged in to Linux. To prevent being logged off while you are working, you may want to set the value to something like TMOUT=1800 (to allow 30 minutes of idle time). You can use any terminal session to close the current shell after a set number of seconds - for example, TMOUT=30.
  
  - PATH - As described earlier, the PATH variable sets the directories that are searched for commands you use. If you often use directories of commands that are not in your path, you can permamnently add them. To do this, add a PATH variable to yuor .bashrc file. For example, to add a directory called /getstuff/bin, add the following:
  
    - PATH+$PATH:/getstuff/bin ; export PATH
  
    ** This above example first reads all the current path directories into the new PATH ($PATH), add the /getstuff/bin directory, and then exports the new PATH.
  
  - **Caution**
    > Some people add the current directory to their PATH by adding a directory identified simply as a dot (.) as follows:
  
      - PATH=,:$PATH  ; export  PATH
  
    > This enables you to run commands in your current directory before evaluating any other command in the path (which people may be used to if they have used DOS). However, the security risk with this procedure is that you could be in a directory that contains a command that you don't intend to run from that directory. For example, a malicious person could put an ls command in a directory that, instead of listing the content of your directory, does something devious. Because of this, the practice of adding the dot to your path is highly discouraged.
  

- You can create your own environment variables to provide shortcuts in your work. Choose any name that is not being used and assign a useful value to it. For example, if you do lots of work with files in the /work/time/files/info/memos directory, you could set the following variable:

  - M=/work/time/files/info/memos ; export M 

- You could make that your current directory by typing cd $M. You could run a program from that directory called hotdog by typing $M/hotdog. You could edit a file from there called bun by typing vi $M/bun.
  
<br />
  
### Getting information about Commands
  
  - When you first start using the shell, it can be intimidating. All you see is a prompt. How do you know which commands are available, which options the use, or how to use advances features? Fortunately, lots of help is available. Here are some places you can look to supplement what you learn here:

  <br />
  
    - **Check the PATH.** Type echo $PATH. You see a list of the directories containing commands that are immediately accessible to you. Listing the contents of hose directories displays most standard Linux commands. For example:
  
      - **ls  /bin** 
        arch      dd            fusermount    loadkeys    mv              rnano 
        awk       df            gawk          login       nano            rmp 
        basename  dmseg         gettext       ls          netstat         rvi 
        bash      dnsdomainname grep          lsblk       nice            rview 
        cat       domainname    gtar          lscgroup    nisdomainname   sed 
        chgrp     echo          gunzip        lssubsys    ping            setfont 
        chmod     ed            gzip          mail        ping6           setserial 
        chown     egrep         hostname      mailx       0ps             sh 
        cp        env           1pcalc        mkdir       pwd             sleep 
        cpio      ex            kbd_mode      mknod       readlink        sort 
        csh       false         keyctl        mktemp      red             stty
        cut       fgrep         kill          more        redhat_lsb_init su 
        dash      find          link          mount       rm              sync
        date      findmnt       ln            mountpoint  rmdir           tar 
  
  <br />
  
  - **Use the help command.** Some commands are built into the shell, so they do not appear in a directory. The help command lists those commands and shows options available with each of them. (Type help | less to page through the list.) For help with a particular built-in command, type the help command, replacing command with the name that interests you. The help command works with the bash shell only.
  
  - **Use --help with the command.** Mnay commands include a --help option that you can use to get information about how the command is used. For example, if you type date --help | less, the output shows not only options, but also time formats you can use with the date command. Other commands simply use a -h option, like fdisk -h.
  
  - **Use the info command.** The info command is another tool for displaying information about commands from the shell. The info command can move along a hierachy of nodes to find information about commands and other items. Not all commands have information available in the info database, but sometmes more information can be found there on a man page.
  
  - **Use the man command.**  To learn more about a particular command, type the man command. (Replace command with the command name that you want.) A description of the command an dits options appears on the screen.
  
  <br />
  
- Man pages are the most common means of getting information about commands, as well as other basic components of a Linux systemm. Each man page falls into one of the categories listsed i Table 3.8. As a regular user, you will be most interested in man pages in section 1. As a system administrator, you will also be interested in sections 5 and 8, and occasionally section 4. Programmers will be interested in section 2 and 3 man pages.
  
--  **Manual Page Sections**
  
| Section Number  | Section Name  | Description |
| --------------  | ------------  | ----------- |
| 1 | User Commands | Commands that can be run from the shell by a regular user (typically no administrative privilege is needed) |
| 2 | System  Calls | Programmin functions used within an application to make calls to the kernel |
| 3 | C Library Functions | Programming functions that provide interfaces to specific programming libraries (such as those for certain graphical interfaces or other libraries that operate in user space)  |
| 4 | Devices and Special Files | Filesystem nodes that represent hardware devices (such as terminals or CD drives) or software devices (such as random number generators)  |
| 5 | File Formats and Conventions  | Types of files (such as graphics or word processing file) or specific configuration files (such as the passwd or group file)  |
  
- ps -p $$ – Display your current shell name reliably.
- echo "$SHELL" – Print the shell for the current user but not necessarily the shell that is running at the movement.
- alias mypass=’/etc/passwd’
  
  

## Moving around the filesystem
  
- In Linux, files are organized within a hierarchy of directories. 

<br />
  
- If you were to map out the files and directories in Linux, it would look like an upside-down tree. At the top is the root directory (not to be confused with the root user), which is represented by a single slash (/). Below that is a set of common directories in the Linux system, such as bin, dev, home, lib, and tmp, to name a few. Each of those directories, as well as directories added to the root directory, can contain sub-directories.  

  ![image](https://user-images.githubusercontent.com/84306023/127815556-c6cff229-59c6-4fce-b200-9dfd806e19ac.png)

  - To access files in the directory joe you can either go in as /home/joe/Documents/memos/memo1.doc or else if you’re let’s say inside the sub-directory “Documents” and then you will only have to navigate to /memos/memo1.doc.
  
  - Some of the Linux Directories that may interest you:
    - /bin - Contains common Linux user commands, such as ls, sort, date, and chmod.
    - /boot - Has the bootable Linux kernel and boot loader configuration files (GRUB).
    - /dev - Contains files representing access points to devices on your systems. These include terminal devices (tty*), floppy disks (fd*), hard disks (hd* or sd*), RAM (ram*), and CD-ROM (cd*). Users can access these devices directly through these devices; however, applications often hide the actuak device names from end users.
    - /etc - Contains administrative configuration files. Most of these files are plaintext files that can be edited with any text editor if the user has proper permission.
    - /home -  Contains directories assigned to each regular user with a login account. (The root user is an exception, using /root as his or her home directory.)
    - /media - Provides a standard location for automounting devices (removable media in particular). If the medium has a volume name, that name is typically used as the mount point. For example, a USB drive with a volume name of myusb would be mounted on /media/myusb.
    - /lib - Contains shared libraries needed by application in /bin and /sbin to boot the system.
    - /mnt - A common mount point for many devices before it was supplanted by the standard /media directory. Some bootable Linux systems still use this directory to mount hard disk partitions and remote filesystems. Many people still use this directory to temporarily mount local or remote filesystems that are not mounted permanently.
    - /misc - A directory sometimes used to automount filesystems upon request.
    - /opt - Directory structure available to store add-on application software.
    - /proc - Contain information about system resources.
    - /root - Represents the root user's home directory. The home directory for root does not reside beneath /home for security reasons.
    - /sbin - Contains administrative commands and daemon processes.
    - /tmp - Contains temporary files used by applications.
    - /usr  - Contains user documentation, games, graphical files (X11), libraries (lib), and a variety of other commands and files that are not needed during the boot process. The /usr directory is meant for files that don't change after installation (in theory, /usr could be mounted read only).
    - /var - Contains directories of data used by various applications. In particular, this is where you would place files that you share as an FTP server (/var/ftp) or a web server (/var/www). It also contains all system log files (/var/log) and spool files in /var/spool (such as mail, cups, and news). The /var directory contains directoriesand files that are meant to change often. On server computers, it is common to create the /var directory as a separate filesystem, using a filesystem type that can be easily expanded.
  
  - The filesystem in the DOS and Microsoft Windows operating systems differ from Linux's file structure, as the sidebar "Linux Filesystems versus Windows-Based Filesystems" expalins.
  
### Linux Filesystems versus Windows-Based Filesystems
  
Although similar in many ways, the Linux filesystem has some striking differences from filesystems used in MS-DOS and Windows operating systems. Here are a few:
  
    - In MS-DOS and Windows filesystems, drive letters represent different storage devices (for example, A: is a floppy drive and C: is a hard disk). In Linux, all storage devices are connected to the filesystem hierachy. SO the fact that all of /usr may be on a separate hard disk or that /mnt/remote1 is a filesystem from another computer is invisible to the user.
  
    - Slashes,r ather than backslashes, are used to separate directory names in Linux. So C:\home\joe in a Microsoft system is /home/joe in a Linux system.
  
    - Filenames almost always have suffixes in DOS (such as .txt for text files or .doc for word-processing files). Although at times you can use convention in Linux, three-character suffixes have no required meaning in Linux. They can be useful for identifying a file tpye. Many Linux applications and desktop environments use file suffixes to determine the contents of a file. In Linux, however, DOS comman extensions such as .com, .exe, and .bat don't necessarily signify an executable (Permission flags make Linux files executable.)
  
    - Every file and directory in a Linux system has permissions and ownership associated with it. Security varies among Microsoft systems. Because DOS and Microsoft Windows began as single-user systems, fiel ownership was not built into those systems when they were designed. Later releases added features such as file and folder attributes to address this problem.
  
<br />
  
**Commands to create and use files**
  
- cd – Changes to another directory.
- pwd – Prints the name of the current or present working directory.
- mkdir – Creates a directory.
- chmod – Changes the permission on a file or directory.
- ls – Lists the contents of a directory.
  

- /usr/share – Represents the absolute path because it begins with a slash (/). 
- cd ~ Takes you to the home directory.
- Use the two dots (..) to go to a directory above the current directory.
  
  - **Exercise**
     1. cd → pwd → mkdir test → ls -ld test
     2. drwxr-xr-x 2 joe sales 1024 Jan 24 12:17 test
     3. This listing shows that test is a directory (d). The d is followed by the permissions (rwxr-xr-x). The owner (joe), the group (sales), and the date that the files in the directory were most recently modified (Jan 24 at 12:17 p.m.).  
  
- Note:
  > In Fedora and Red Hat ENterprise Linux, when you add a new user, the user is assigned to a group of the same name by defualt. For example, in the preceding text, the user joe would be assigned to the group joe. This approach to assigning groups is referred to as the user private group scheme.
  
    - chmod 700 test (This step changes the permissions of the directory to give you complete access and everyone else no access at all. (The new permissions should read rwx------.)
    - $ cd test
    - $ pwd
      - /home/joe/test  
  
### Using Metacharacters and Operators
  
- Whether you are lisitng, moving, copying, removing, or otherwise acting on files in your Linux system, certain special characters, referred to as metacharacters and operators, elp you to work with files more efficiently. Metacharacters can help you match one or more files without completely typing each file name. Operators enable you to direct information from one command or file to another command or file.
  
#### Using file-matching metacharacters

-  To save you some keystrokes and to enable you to refer easily to a group of files, the bash shell lets you use metacharacters. Any time you need to refer to a fiel or directory, such as to list it, open it, or remove it, you can use metacharacters to match the files you want. Here are some useful metacharacters for matching filenames:
  
   - *-Matches any number of characters.
   - ?-Matches any one character.
    - [...]-Matches any one of the characters between the brackets, which can include a hyphen-separated range of letters or numbers.
  
- Exercise
  --------
  1. touch apple banana grape grapefruit watermelon. (Please be aware that the touch command creates empty files.)
  2. ls a* (any file that begins with a).
  3. ls g* (any file that begins with g).
  4. ls g*t (any file that begins with g and ends with t).
  5. ls *e* (any file that contains e in the name is matched, can also be as ls *e*r*).
  6. ls *n* (any file that contains n is matched).
  
<br />
  
- Here are a few examples of pattern matching with the question mark (?):
  - $ ls ????e
    - apple grape

  - $ ls g???e*
    - grape grapefruit
  
  > The first example matches any five-character file that ends in e (apple, grape). The second example matches any file that begins with g and has e as its fifth character (grape, grapefruit).
  
  <br />
  
  - The following examples use braces to do pattern matching:
    - $ ls [abw]*
      - apple banana watermelon
  
    - $ ls [agw]*[ne]
      - apple grape watermelon
 <br />
  
  > In the first example, any file beginning with a, b, or w is matched. In the second, any file that begins with a, g, or w and also ends with either n or e is matched. You can also include ranges within brackets. For example:
    - $ ls [a-g]*
      - apple banana grape grapefruit
        > Here, any filenames beginning with a letter from a through g are matched. 
  
-------
  
### Using file-redirection metacharacters

- Using pipes, you can direct standard output from one command to the standard input of another. 
  
- With files, you can use less than (<) and greater than (>) signs to direct data to and from files. Here are the file-redirection characters: 
  
  -  <— Directs the contents of a file to the command. In most cases, this is the default action expected by the command and the use of the character is optional; using less bigfile is the same as less < bigfile. 
  -  >— Directs the standard output of a command to a file. If the file exists, the content of that file is overwritten.
  -  2>— Directs standard error (error messages) to the file. 
  -  &>—Directs both standard output and standard error to the file. 
  -  >>—Directs the output of a command to a file, adding the output to the end of the existing file.  


> A command when wanting to open the file explorer with root permissions: 
  - sudo apt install mailutils

<br />
 
 Examples
------
  
  
- $ mail root < ~/.bashrc (The content of the .bashrc file in the home directory is sent in a mail message to the computer’s root user.) 
- $ man chmod | col -b > /tmp/chmod (Formats the chmod man page (using the man command), removes extra back spaces (col -b), and sends the output to the file /tmp/chmod (erasing the previous /tmp/chmod file, if it exists) 
- $ echo "I finished the project on $(date(+%d)" >> ~/projects 
(Results in the following text being added to the user’s project file:
  - I finished the project on Sat Sep 6 13:46:49 EDT 2015 )
  

  - Another type of redirection, referred to as here text (also called a here document), enables you to type text that can be used as standard input for a command. Here documents involve entering two-less than characters (<<) after a command, followed by a word. All typing following that word is taken as user input until the word is repeated on a line by itself. Here is an example:
      
      <br />
      > $ mail root jibs ops dev <<the text
      <br />
      > I want to tell everyone that there will be a 10 a.m.
      <br />
      > meeting in conference room B. Everyone must attend thsi meeting.
      <br />
      > --James
      <br />
      > thetext
      <br />
      $
  <br />
  
  - This example send a mail to jibs, ops, and dev usernames. The tetx entered between <<thetext and the tetx becomes the content of themessage. A common use of here text is to use it with a text editor to create or add to a file from within a script:
    
    - /bin/ed /etc/resolv.conf  <<resendit
      a
      nameserver 100.100.100.100
      .
      w
      q
      resendit
  
  - With these lines added to a script run by the root user, the ed text editor adds the IP address of a DNS server to the /etc/resolv.conf file.
  
  
### Using brace expansion characters

- By using curly braces ({}), you can expand out a set of characters across filenames, directory names, or other arguments you give commands. For example, if you want to create a set of files such as memo1 through memo5, you can do that as follows:
    
    - $ touch memo{1,2,3,4,5}
    - $ ls
      <br />    
      memo1 memo2 memo3 memo4 memo5
  
![image](https://user-images.githubusercontent.com/84306023/128028440-51c06011-3cf2-47bc-911f-68fc27cc14f3.png)

  - To see if ls is aliased: type alias ls (The --color=auto option causes different types of files and directories to be displayed in different colors.)
  
  
Exercise
--------

  1. cd $HOME/test
  2. $ cd $HOME/test
  3. $ touch scriptx.sh apple
  4. $ chmod 755 scriptx.sh
  5. $ mkdir Stuff
  6. $ ln -s apple pointer_to_apple
  7. $ ls
  <br />
  apple pointer_to_apple scriptx.sh Stuff 
  

  > The directory docs shows up in blue, pointer_to_apple (a symbolic link) appears as aqua, and scriptx.sh (which is an executable file) appears in green. All other regular files show up in black. 
Typing ls -lto see a long listing of those files can make these different types of files still clearer:

  $ ls -l
  total 4
  -rw-rw-r--. 1 joe joe 0 Dec 18 13:38 apple
  lrwxrwxrwx. 1 joe joe 5 Dec 18 13:46 pointer_to_apple -> apple
  -rwxr-xr-x. 1 joe joe 0 Dec 18 13:37 scriptx.sh
  drwxrwxr-x. 2 joe joe 4096 Dec 18 13:38 Stuff 
  
  > A hyphen (-) indicates a regular file, d indicates a directory, and l ( lowercase L) indicates a symbolic link. An executable file (a script or a binary file that runs as a command) has execute bits turned on (x).

  ![image](https://user-images.githubusercontent.com/84306023/128029040-2272f66e-58e2-49c3-ba5f-53a74aed38f9.png)

> Displaying a long list (-l option) of the contents of your home directory shows you more about file sizes and directories. The total line shows the total amount of disk space used by the files in the list (158 kilobytes in this example). Directories such as the current directory (.) and the parent directory (..)—the directory above the current directory—are noted as directories by the letter d at the beginning of each entry. Each directory begins with a d and each file begins with a dash (-). The file and directory names are shown in column 7. In this example, a dot (.) represents /home/joe and two dots (..) represent /home—the parent directory of /joe. Most of the files in this example are dot (.).
  
> In addition to the d or -, column 1 on each line contains the permissions set for that file or directory. Other information in the listing includes the number of hard links to the item (column 2), the size of each file in bytes (column 5), and the date and time each file was most recently modified (column 6). 
  
> Though the number can grow above 4096 bytes for a directory that contains lots of files, this number doesn’t reflect the size of files contained in that directory. 
  
> On occasion, instead of seeing the execute bit (x) set on an executable file, you may see an s in that spot instead. With an s appearing within either the owner (-rwsr-xr-x) or group (-rwxr-sr-x) permissions, or both (-rwsr-sr-x).
  
> If a t appears at the end of a directory, it indicates that the sticky bit is set for that directory (for example, drwxrwxr-t). By setting the sticky bit on a directory, the directory’s owner can allow other users and groups to add files to the directory, but prevent users from deleting each other’s files in that directory. With a set GID assigned to a directory, any files created in that directory are assigned the same group as the directory’s group. (If you see a capital S or T instead of the execute bits on a directory, it means that the set GID or stick bit permission, respectively, was set, but for some reason the execute bit was not also turned on.).
  
> If you see a plus sign at the end of the permission bits (for example, -rw-rw-r--+), it means that extended attributes, such as Access Control Lists (ACLs) or SELinux, are set on the file.  
  
![image](https://user-images.githubusercontent.com/84306023/128029416-230e190d-3841-41c0-9cd1-b2d7fb00cb76.png)

  
- ls -a = Any file or directory beginning with a dot (.) that are typically configuration files or directories. 
  
- The -t option displays files in the order in which they were most recently modified. With the -F option, a backslash (/) appears at the end of directory names, an asterisk (*) is added to executable files, and an at sign (@) is shown next to symbolic links. 

- To list files and append file-type indicators:
  
  ![image](https://user-images.githubusercontent.com/84306023/128029688-d365afe1-ec60-4f68-b88d-06d644c657e4.png)

- The nine bits assigned to each file for permissions define the access that you and the others have to your file. Permission bits for a regular file appear as -rwxrwxrwx. Those bits are used to   define who can read, write, or execute the file.
  
![image](https://user-images.githubusercontent.com/84306023/128029774-7115b4ce-d0bb-45ff-a832-600dda9dcaeb.png)

  ![image](https://user-images.githubusercontent.com/84306023/128029807-440834d7-af0b-4ee0-849b-28f9fb661d3d.png)

  - You can see the permission for any file or directory by typing the ls -ld command. 
    - $ ls -ld ch3 test
      <br />
      -rw-rw-r-- 1 joe sales 4983 Jan 18 22:13 ch3
      drwxr-xr-x 2 joe sales 1024 Jan 24 13:47 test 


  ![image](https://user-images.githubusercontent.com/84306023/128029961-fab8e807-3922-4ecc-965a-49367583a43d.png)

  ![image](https://user-images.githubusercontent.com/84306023/128029992-cd3925bf-e8ba-444d-9f7b-906d0ce91a09.png)

  
  ![image](https://user-images.githubusercontent.com/84306023/128030045-a1d5e51c-0b5c-4d39-b228-857af8bbc8b8.png)

- sudoers.d example

### Setting default file permission with umask
  
  - When you create a file as a regular user, it’s given permission rw-rw-r-- by default. A directory is given the permission rwxrwxr-x. For the root user, file and directory permission are rw-r--r-- and rwxr-xr-x, respectively. These default values are determined by the value of umask.
    - $ umask
      <br />
      0002 
  
![image](https://user-images.githubusercontent.com/84306023/128030362-4c051c50-5455-40f7-881f-88a94f9047b7.png)

![image](https://user-images.githubusercontent.com/84306023/128030391-9cb3f543-4809-422f-8ac4-6804d5faf176.png)
  
![image](https://user-images.githubusercontent.com/84306023/128030788-b42c10f4-a90b-4844-8f67-9a505e1b103b.png)

![image](https://user-images.githubusercontent.com/84306023/128030811-2ff65b1d-f175-4ced-ab06-4ad20a8e241e.png)


    

  
  
  
  



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



