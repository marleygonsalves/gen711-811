# Lab3 - 2/6/26

## Before lab begins
1. Open up vscode
2. Control + shift + 'p' to open command prompt (command + shift + p on apple)
3. Start typing 'Connect to...' and the 'Connect current window to host' menu item will pop up. Select it
4. If asked, connect to 'ron.sr.edu host'
5. Enter your RON username if prompted
6. Enter your RON password when prompted
7. Go to 'File --> Open folder'
8. Select your 'gen711-811' directory
9. If you haven't done so already, save your workspace to this directory (File --> save directory as --> enter)
10. Take your notes in 'Markdown' format. See the readme.txt for taking notes for this lab below. 

# Part 1 (lab 3)
### Questions:
- What is a command shell and why would I use one?
- How can I move around on my computer?
- How can I see what files and directories I have?
- How can I specify the location of a file or directory on my computer?

### Objectives:
- Describe key reasons for learning shell.
- Navigate your file system using the command line.
- Access and read help files for bash programs and use help files to identify useful command options.
- Demonstrate the use of tab completion, and explain its advantages.

## The key points here are:
- The shell gives you the ability to work more efficiently by using keyboard commands rather than a GUI.
- Useful commands for navigating your file system include: ls, pwd, and cd.
- Most commands take options (flags) which begin with a -.
- Tab completion can reduce errors from mistyping and make work more efficient in the shell.

# Navigating Files and Directories
- How can I perform operations on files outside of my working directory?
- What are some navigational shortcuts I can use to make my work more efficient?

# Part 2 (lab 3)
## Objectives:
- Use a single command to navigate multiple steps in your directory structure, including moving backwards (one level up).
- Perform operations on files in directories outside your working directory.
- Work with hidden directories and hidden files.
- Interconvert between absolute and relative paths.
- Employ navigational shortcuts to move around your file system.

## More navigation
- We got an idea for moving around using cd and the name of the folder to move into. 
- But how to we go back out? We dont see the folder we are in.
- We have a special command to tell the computer to move us back or up one directory level.

### Your Notes Here: 

- Using a dash is helpful for lists
1. And numbers for lists

The pound sign is used for 'sections'. A single pound (or hashtag) in front of a word makes it appear bigger/bold to show a new section. See below

# My Notes (example):

To change directories, use 'cd' and then hit tab two times to see directories in my current directory

# My Notes 

- This is where we will take notes for lab. We will take notes for the day in each lab document, then transfer the important stuff to the official lab notebook, which will be used during practicals. Actual protocol is TBD. 
- Formatting: use - or numbers for lists. Create a bolded section header using #. See above. 

Today we are learning how to move around the command line. Here are some important commands. 

- pwd: print working directory. This tells you where you are in your Ron. pwd prints out: /home/users/mgg1026/gen711-811 since I am in my gen711-811 directory. 
- ls: list. This tells me everything that is in my directory, or whatever directory I am currently in. 
- clear: this clears out the command line (moves you down)
if you end a command with a ' you will get a bunch of < on new lines, no matter what you type. You can type the other ' to esacpe. If you get stuck you can type ^C to escape, or ctrl + C to escape. 
- cd: this moves you around. cd DIRECTORY/FILE moves you into that file or directory. 
- to specific options it is command -letter. ls -F tells you if things are directories or files, directories will end with /
- man: manual, will give you the manual for whatever command you do next. some of this is confusing. you can also google it. 
- q: quit something in command line
- ls -lrth: prints info about all the stuff in whatever directory you're in, also orders them with newest at the bottom
press tab to autocomplete. you should do this!
- head file: spits out 10 lines of the file. head SRR097977.fastq gives the first 10 lines of a FASTQ file (id, sequence, quality)
- cd ../: send you back one directory. cd ../../ will send you back two, etc. 

when you log in you go into home directory (mgg1026)
- cd ~: this brings you right to your home directory 
- cd $HOME: also brings you home

relative paths: tells you where to go based on where you are. 
pwd gives absolute path, since it starts at the beginnign of the computer. absolute paths can also bring you to where you want to go with cd 

grep. searches a file and returns only what contains what you're looking for
- grep '@' SRR097977.fastq  searches for @ in the file. gives you the lines that contains @. This command gave a quality score line, because @ was a quaity score. 
- grep '^@' SRR097977.fastq, ^ says to look for the next character at the start of the line. or make it more specific, and do the whole file. the chance that the quality score would = the file name is low. 

What if we want to make the grep output into a file? redirect into a file!
- grep '@SRR097977' SRR097977.fastq > headerlines.txt: this says search for this stuff in this file, then put it into a file. That makes a file in whatever directory you're in

- ls *fastq: ls things that end with whatever you put behind *

- | pipes the output of one command to the next command. ls /bin/c* | wc -l does the ls then puts that into wc -l that counts it (word count, gives lines, words, characters)

ls /bin/ | grep '^c' | wc -l does the same thing, lists the things in bin, pulls up the ones that start with c, counts them, > file would put that into a file. 

### Complete the questions below when intrstructed. Push the changes to this document to recive credit for attending the lab

#### 1. What are 3 ways to change directories to your home directory from the  untrimmed_fastq directory?
1. cd $HOME
2. cd ~
3. cd ../../../
4. absolute path: cd /home/users/mgg1026

#### 2. How many programs in /bin 
/bin is a directory of programs on RON
2. Do each of the following tasks from your current directory using a single ls command for each:
    - List all of the files in /bin that start with the letter ‘c’.
        ls c*, ls c* | wc -1 to count
    - List all of the files in /bin that contain the letter ‘a’.
    - List all of the files in /bin that end with the letter ‘o’.
    - Bonus: List all of the files in /bin that contain the letter ‘a’ or the letter ‘c’.

#### Answers here
Start with the letter c ____ ls c* (94)
Contain the letter a ____ ls *a* (633)
End with the letter o ____ ls *o (34)
Contain the letter ‘a’ or the letter ‘c’ ____ ls *[ac]* (926)

#### What command/commands would you use to find the line number in your history for the command that listed all the '.fastq' files using the absolute path. Paste your answer below.

I made a txt tile with history, 
    history > history.txt
Then searched for the command
    grep '' history.txt

pipe history into a grep searching for the command. I didn't do the command so i am not typing it here. my computer died before i could save (eek) but it was fine. Yay!