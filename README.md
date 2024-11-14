# GNU-Presentation
## Basic file editing
Vi is a text editor for the console. Of course vi editor has alot of keyboard shortcuts and can not be compared with other text editors on graphical desktops where we can use underline text. Nevertheless, vi is very extensive and is a standard text editor under linux. An improved version of vi is the vim and can be install using the command **sudo apt install vim**.
Vi can be started in two ways; either by typing just **vi** on the terminal and pressing the **enter** key or typing **vi** with an appropriate named file like  **vi mynewtextfile**. Vi has two execution mode namely **the Normal mode(commnand mode) and the input mode(insert mode)** meanwhile the **Normal mode** is the default mode once you enter the **vi** editor. While in **Normal mode**, you can comfortably make use of some keys to delete, copy, paste among others but can not enter text because **vi** does not see certain letters as words but as commands. Below are some important keys and its functions which help you to navigate the **vi** editor seamlessly.
- **h, j, k, l** keys is use to move left, down, up and right respectively
- **:q** key is use to exit the editor. However if we exit **vi** without saving, the empty file will not be created
- **a** key is use to enter the input mode after the current cursor position
- **A** key ensures that the cursor jumps to the end of the current line
- **G** key jumps to the last line of in the first position
- **gg** keys jumps back to the top left of the first line
- **o** key ensures a blank line inserted below the current line
- **O** key ensures a blank line is inserted above the current line
- **:q!** ensures the file is not saved even after modification
- **:wq** ensures the file is saved and written out of it
- **:w** just save the file but  do not exit it
- **ZZ** ensures the file is saved and exited
- **:x** ensures the file is saved and exited
- **yy** copy a line
- **p** ensures copied content is paste after the current position
- **P** ensures copied content is paste before the current position
- **x** deletes the chracter under the cursor
- **u** undo the last action performed
- **e** go to the end of the current word
-   **w** jumps to the start of each line
-   **dw** delete one word
-   **dd** delete one line
-   **H** will go the number of lines specified e.g 5H from the top of the screen
-   **L** will move the cursor to the line specified e.g 3L to the last line of the screen
-   **/** used for a forward search
-   **?** used for a backward
-   **WQ** is used to close and do not save

It should be worth noting that search works only in normal mode and not insert mode.
**Objectives** 
- Navigate a document using vi.
- Understand and use vi modes.
- Insert, edit, delete, copy and find text in vi.
- Awareness of Emacs, nano and vim.
- Configure the standard editor.

vi
/, ?
h,j,k,l
i, o, a
d, p, y, dd, yy
ZZ, :w!, :q!
  
 ### Introduction 
As any other tool, we have a wide range of selection when it comes to text editors. One of the most common and super powerful choices is the vi editor. It is pre-installed on all major Linux distributions and you can be sure that knowing it, will let you edit your files on all environment. Here is an Improved version of vi which is called VIMproved or vim. Sometimes thats what you will find on your system and sometimes the vi
command is aliased or linked to vim.

 **vi modes** 
vi works in two modes:
1. Command mode is where you go around the file, search, delete text, copy paste, replace, ... and give other commands to the vi. Some
commands start with a : and some are only a keypress.
2. Insert mode is where what you type, goes into the file at the cursors position.

To switch to the Command mode, press the ESC key. To go back to the Insert mode, you can use several commands but one common
one is pressing the i key.

 **Moving the cursor** 

To move around a text file, use these keys in Command mode. The key functions are:
- h One character to the left (only current line)
- j One line down
- k One line up
- l One character to the right (only current line)
- w Next word on the current line
- e Next end of word on the current line
- b Previous beginning of the word on the current line
- Ctrl-f Scroll forward one page
- Ctrl-b Scroll backward one page
Typing a number before most commands will repeat the command that many times (i.e. 6h will go 6 characters to the left)

**Jumping around**
The key functions are:
- G With no number, will jump to the end & 10G will jump to line 10
- H 5H will go to the 5th line from the top of the screen
- L 3L will move the cursor to the 3rd line to the last line of the screen

 **Editing text** 
These commands during the command mode will help you enter, edit, replace and text:
key functions
- i Enter the insert mode
- a Enter the insert mode after the current position of the cursor
- r replace only one character
- o open a new line below the cursor and go to the insert mode
- O open a new line above the cursor and go to the insert mode
- c clear to a location and go to the insert mode the replace till there and then normal insert (cw will overwrite the current word)
- d delete. you can mix with w (dw) to delete a word. Same as cw but dw does not go to the insert mode
- dd Delete the current line
- x Delete character at the position of the cursor
- p Paste the last deleted text after the cursor
- P Paste the last deleted text before the cursor
- xp swaps the character at the cursor position with the one on its right

**Searching**
The key functions are:
- / Search forward (/happiness will find the next happiness)
- ? Search backward
- n repeat previous search.
  
**Exiting**
It is always funny when you see someone entering to the vi and not knowing how to exit! Learn these and prevent the laughter, the key functions are:
- **:q!** Quit editing without saving = runaway after any mistake
- **:w** mynewtextfile.txt Write to a new name if you wish
- **ZZ** Exit and save the file if modified
- **:e!** Reload the file from disk
- **:!** Run a shell command
Entering colon (:) during command mode will move the cursor to the bottom of the screen and vi will wait for your commands. Press ESC to return back to the normal command mode.The exclamation mark in most commands will say "I know what I'm doing" and will write on read-only files if you have access and will exit without asking
it is possible to combine commands. For example you can combine :w and :q and just say :wq (write and exit).
**help** You can always ask for help with **:help** or **:help subject**. This way vi will open a help text which you can use **/** search just like any other text. Close it with **:q** command.

**Other editors**
You can also use other editors if you want. One easy to use and common option is nano and some other choices are micro, emacs (full featured) and
neovim (an update to vim).
 
**Default editor** 
The default editor in bash is set using the EDITOR environment variable. You can change it with: **export EDITOR='vim'** by adding the above line to the .bashrc file.

## change process execution priorities (nice, renice, ps and top)

**Objectives** 
- Know the default priority of a job that is created.
- Run a program with higher or lower priority than the default.
- Change the priority of a running process.
 
On a Linux machine, you might have 100s of processes running at the same time and competing for more CPU & RAM. The good news is that you can give some of the processes higher or lower priority (or nice-ness) in this competition. Let's have a look at a sample **top** output..

The **NI** column shows how nice this process is. The nicer the process, the less CPU it asks. The nice values can be from -20 to 19 . To interpret this value, look at it like this: a process with nice = -20 is **ANGRY** and gets more priority for CPU and RAM while a process with nice = 19 is **SUPER NICE** and lets other processes use the resources before her). The default value for **nice** is normally set to 0; this can be checked with **nice**  command. You can also check the nice-ness using the ps command: **ps -l** 

 **Setting nice-ness** 
If you need to change the niceness level of a program you can run it with nice command and -n switch (for nice):  e.g **nice -n 19 echo "I am running!"** and the output will be I am running! , **nice -n -20 echo "I am running!"** and you will see **nice: cannot set niceness: Permission denied** together with **I am running!**. Another example is, **sudo nice -n -20 echo "I am running!"** and you now see the change nice value together with **I am running!**. As you can see in the above example, only the root can issue high-priority niceness (below 0). However, if you run a command with nice without -n, the default will be -n 10.

The **renice** command can be used to change the niceness of your running processes (or others if you are root): example: **sudo renice -n  <PID>**

