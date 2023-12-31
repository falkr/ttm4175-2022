# Day 2: The Linux Terminal

Today, many of you will take your first steps with the powerful Linux terminal.

### Learning Goals

:goals:
- Become familiar with Linux commands and the terminal
- Feel at home on the Raspberry Pi
- Understand user permissions


### New Linux Commands

- [cat](commands.html#cat) --- concatenate files (and lots more) 
- [cd](commands.html#cd) --- change into another directory 
- [curl](commands.html#curl) --- powerful tool for web requests, among other to download a file
- [ls](commands.html#ls) --- list files and folders
- [pwd](commands.html#pwd) --- show in which directory you are
- [sudo](commands.html#sudo) --- running commands as super user
- [mkdir](commands.html#mkdir) --- create a folder
- [rmdir](commands.html#rmdir) --- remove a folder
- [rm](commands.html#sudo) --- remove a file
- [touch](commands.html#sudo) --- create a file
- [grep](commands.html#grep) --- search for text in a file


At the top of the page with the list of commands, we [listed three ways to find more about commands](commands.html): `man`, `apropos` and the `--help` option.



# Navigating Folders and Files

On Linux, **files** are sorted in **folders**, just like you are used to from other computers. 
Sometimes, _folder_ are also called _directories_. 
Since folders can be other folders, this creates a tree-like hierarchy. 
Each file and folder therefore has a **path**.

The path of the home directory, for instance, is in `/home/pi`, for the default user with the name `pi`.
There are two things about paths you need to remember:

- They start with a `/` in the beginning, this is the topmost folder. This topmost folder is also called _root_ folder.
- The different folders and files are separated by `/`.


### Find out where you are with pwd

When you are in the terminal, you are always in some folder. When you boot up and just open a terminal, you usually start in the home folder. If you are not sure, where you are currently, type the `pwd`command, which stands for _"**p**rint **w**orking **d**irectory"_.

```bash
pwd
```

The output of this command will then be the path of the current folder you are in.

### Change the folder with cd

Using the `cd` command, which stands for _"**c**hange **d**irectory"_, you can change into any riectory, using its path. Type the following to move into your home folder:

```bash
cd /home/pi
```

Since the home folder is so so useful, its path has an abbreviation, which is the funny snake `~` (tilde). You can hence also write the following to change into the home directory:

```bash
cd ~
```

If you want to move just one folder up in the hierarchy, for example, you are in `/home/pi` but would like to go into `/home/`, you can do that with the special path `..`. Here, the `..` just means "one up". So, we can type the following:

```bash
cd ..
```

This moves you one folder up. You can check where you are using the `pwd` command. 

### Listing Folder Content with ls

To look at the files and folders inside a folder use the `ls` command. (Remember it with the word _"**l**i**s**t"_.) For example, move into the root folder at the top and see which files and folders are listed there:

```bash
cd /
```

and then 

```bash
ls
```

will list the following:

---
type: figure
source: figures/teknostart/rpi-terminal-folders-1.png
---

Note that there are different colors for folders and files. 

If you want some more detailed information about folders and files, you can use the `ls -l` command, that means, the `ls` command with an **option** `-l`. When you invoke it in the root folder, for instance:

```bash
ls -l
```

now the listing will look as follows:

---
type: figure
source: figures/teknostart/rpi-terminal-folders-2.png
---

# Creating Folders and Files

### touch and rm

You can create a file with the command `touch`. The created file is empty, but you can then use other programs, for example a text editor, to add content to it.

```bash 
touch file.txt
```

With the `rm` _("**r**e**m**ove")_, you can delete a file:

```bash 
rm file.txt
```

:tip: Be careful with the **rm** command. You can destroy your system when you delete the wrong files. You won't get them back.


### mkdir and rmdir

You can create a folder or directory with the `mkdir` command. _("**m**a**k**e **dir**ectory")_

```bash
mkdir mydirectory
```

With the `rmdir` _("**r**e**m**ove **dir**ectory")_ command, you can delete a directory

```bash
rmdir mydirectory
```



# Advanced File Stuff

### grep

With the `grep` command, you can read a file and out put all lines that match a certain criteria. 
For example, the following command finds all lines that include the string `hello` in the file `log.txt`.

```bash
grep hello log.txt
```


### cat

With the `cat` command, you can simply view the contents of a file. The following will print the contents of the file `log.txt`.

```bash
cat log.txt
```


# Being Super User

Some commands or programs require special permissions to run, usually because they affect more than one user or handle critical resources, or are related to the security of the system.
As the user `pi`, you _have_ all these permissions, but to protect you from doing something stupid, you need to prove to the system that you are allowed to execute these specific commands or programs. For that, the command `sudo` exists, which stands for _"**s**uper **u**ser **do**"_. Sometimes you just add this in front of another command that you want to execute with special rights. 

```bash
sudo <important command...>
```

Think of it as when your parents told you to say "Please!"



# Command Memory

Go through the command descriptions above. Read together as good as it works, repeat reading this on your own as homework. You can use the commands 
[listed here](commands.html) to get help with the solutions.

Use the scissors and create a stack of cards. 


## Round 1: Commands and their Purpose

:steps:
- Create one stack of cards, place the command keywords facing up. 
- Shuffle them a bit.
- Each of you should draw the top card, read the command keyword, and tell the others (without looking) what the command is used for.
- Turn the card around to see if you were right. If not, put the card to the end of the stack.
- Repeat until you went through all cards.

---
type: figure
source: figures/teknostart/command-memory-1.jpg
---


## Round 2: Which command to use?

:steps: 
- Place all cards with the command facing upwards on the table.
- Read the list below, and find the proper command.
- Only if you agree in team, turn the card around and see if you were right.

---
type: figure
source: figures/teknostart/command-memory-2.jpg
---


The commands you should look for:

  1. change into another directory	
  2. create a new empty file	
  3. delete a directory
  4. delete a file	
  5. download a file from a web address	
  6. find lines in a file	
  7. list the contents of a directory	
  8. make a new directory	
  9. print the contents of a file	
  10. read the help for a command
  11. run a command as super user
  12. search in help pages


# Capture the Flag

Capture the Flag (CTF) is a special kind of information security competition. The goal is to collect passwords, or **flags** to progress. There are three common types of CTFs: Jeopardy, Attack-Defence and mixed.

- Jeopardy-style CTFs has a couple of questions (tasks) in range of categories. For example, Web, Forensic, Crypto, Binary or something else. A team gets some points for every solved task. Generally teams will be awarded more points for more difficult tasks. The next task in the chain will be unlocked after you solve the previous one. The team with the most points when the time is over is the winner. A famous example of this kind of CTF is the DEFCON CTF Qualifier.
- Attack-defence is another interesting kind of competition. Here every team has their own network, with many machines, or a single computer, with vulnerable services. The teams are given an amount of time to patch services and secure the network or system and developing exploits to hack the systems of other teams.  So, then organizers connects participants of competition and the wargame starts! You should protect own services for defence points and hack opponents for attack points. Historically this is a first type of CTFs, everybody knows about DEF CON CTF - something like a World Cup of all other competitions.

Today we are going to do a relatively short Jeopardy-style CTF. The category is Linux, which means that the security aspect of the CTF is not really present. It is more of a way to become more familiar with the terminal and navigation around the Linux file structure. The game consists of 12 levels that are supposed to make you feel a little more comfortable using the Terminal as a tool for the Linux Command Line. The first level is used as an example to show how the game is run.


## Preparing the CTF
### Step 1: Move to the Home Directory

Open the terminal and check in which folder you are. We do that with the command `pwd` (_"print working directory"_):

```bash
pwd
````

The output shows in which folder or directory  you are. Move into your home directory, using the `cd` (_"change directory"_) command:

```bash
cd /home/pi/
````

:tip: You can also move to the home directory by writing `cd ~`. The wiggly line that looks like a snake is called _tilde_ and an abbreviation for your home directory.


### Step 2: Download CTF


We now download the file containing the CTF program. 

```bash
curl https://home.samfundet.no/~halvogro/ting/teknostart_ctf.zip -O
```

:tip: When you download such a file and then run it, you need to make sure that you know what it contains or trust its origin. The file can run programs that have access to everything on your computer. 


### Step 3: Install and run

With `curl`, you downloaded a zip file. All the files needed for the CTF is here. 

1. Unzip the files by typing `unzip teknostart_ctf.zip`

To be able to run the program we first need to some files.

2. Type `cd teknostart_ctf` to change directory to the folder you just unzipped. 
3. Type `pwd` and confirm that you are inside the `/home/pi/teknostart_ctf` folder. 

Here there are three files that are important for the CTF:

- `teknostart_ctf.py`, which is the actual CTF program, it will be demonstrated later how to use it.
-  This is a terminal based game and is written in the programming language [Python]((https://www.python.org/))
- `levelcheck` is needed for some levels and checks if the tasks has been completed. It prints out the flag if the task has been done correctly. Used to retrieve the flag (password) for some levels, where it has to be checked whether you completed the task correctly.
- `install` is an executable program that is only going to be run once to set everything up. 

To run an executable file in the folder that you are currently in, we type `./` followed by the name of the program.

4. Type `./install` to run the installer.

Now we are ready to begin the CTF.

# Example: First CTF Task

### Step 1

Run the program for the first time:

```bash
./teknostart_ctf.py
```

You should get an output back that looks like this. 

```
CURRENT LEVEL: level 1

----------------------------------------

In which folder are you located when you open the terminal?

Example answer:      /folder/folder      
Answer given:        None                
Hash of answer:      dc937b59892604f5a86ac96936cd7ff09e25f18ae6b758e8014a24c7fa039e91
Correct hash:        1c4d3877bf4fe64f9d55cdbbf10d9b02c329b2a5a162ae3014b83da8c3024a71
Levelchecker:        NO                  

----------------------------------------

```

- `CURRENT LEVEL` *is the level that you are currently on, this will increase as you progress*
- `Question` *is the task for this level, read it carefully* 
- `Example answer` *is an example answer to give you an idea of what format the answer should be. for instance, when asked about a file name, this example tries to show that we are looking for the full filename, including the file ending `.txt`.*
- `Answer given` *is the answer you gave, which is "None" by default*
- `Hash of answer` *is a hashed version of your answer. The game takes the answer that you put in, does some math on it, and generates a  [string](https://en.wikipedia.org/wiki/String_(computer_science)) which it will try to compare to the hashed version of the correct answer.* 
- `Correct hash` *is the hashed version of the correct answer. If this hash matches the hash of your answer, the answer is correct*
- `levelcheck` *Tells you if you have to get check that you done the task correctly.*
-- The value is either `YES` or `NO` for each level. If this says `YES`, it means you have to navigate to `/home/pi/teknostart_ctf` and run `./levelcheck` to check that you have completed the task correctly. If you have, you will get the password (flag) to progress to the next level. 


### Step 2: Solve the task

The first you will see is what level you are on, in this case, level 1. As you progress, this will increase. Next is the challenge for this level. This question asks for the folder path that you are in when you each time you launch a new terminal.

First we open a new terminal:
![alt text](https://home.samfundet.no/~halvogro/ting/bilder/image-47.png)

Now, to check which folder location we are in, we type `pwd`

![alt text](https://home.samfundet.no/~halvogro/ting/bilder/image-48.png)

As we can see, we are located in `/home/pi`. 

### Step 3: Check if you got the correct answer

To test our answer, we run the program again and input our answer `/home/pi`.

First we change directory back to where the program `teknostart_ctf.py` is located.

Because we are already inside the folder `/home/pi` we can simply type `cd teknostart_ctf`, which will put us in  `/home/pi/teknostart_ctf`. 

When we now type `ls` to list the files in the directory, we se our `teknostart_ctf.py`file.
![alt text](https://home.samfundet.no/~halvogro/ting/bilder/image-50.png)

We can now run it, and input our answer `/home/pi`.
![alt text](https://home.samfundet.no/~halvogro/ting/bilder/image-52.png)

Success! We had the right flag. The next task is given to us, try to solve that and as many of the following tasks as you can.


# Final Steps

### Learning Goals

In your double-team, reflect about what you learned today. Write a few sentences that capture (in your own words) what you learned and why it can be useful. Share these few sentences with everyone in the double-team. (You should use this text in the individual reflection below.)

:aside: <img src="figures/doubleteam.png" width="30"/>


### Individual Reflection

Fill out the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=cgahCS-CZ0SluluzdZZ8BSxiepoCd7lKk70IThBWqdJUQzJJUEVaQlBBMlFaSFBaTllITkcxRDEzNi4u" class="arrow">individual reflection survey</a>.


### Cleaning Up

:todo:
- Put all hardware back into the box.
- Store the box in one of the lockers in the lab, using the combination lock.
- Connect all parts of the PC back to it (keyboard, mouse, monitor).
- Take out any trash. (Even if its not yours... thank you!)
- Put the chairs back to the table.

### Individual Exercises

We recommend that you take some time to consider if there are any parts of this unit that you want to repeat individually, at your own pace. If you decide to do so, you have several options:

- You have access to the hardware box at all times from the lockers. Just make sure everyone in your team knows where the box is, and put it back into the locker.
- Install a Raspberry Pi Image on a Virtual Box in your PC. With this, you always have a Raspberry Pi with you.
- Some of the Linux-related exercises also work on the Linux-PCs in the lab.
