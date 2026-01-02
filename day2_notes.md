Day 2, 01/01/2026. Linux navigation and file system basics

What I did:
-I completed TryHackMe Linux Funddamentals Part 1
-Practiced navigation system in WSL
- Created, edited and deleted files and directories
- Navigated, created, edited and saved tis note to my GitHub

Commands practiced:
- pwd> show me where I am
- ls> list documents in this directory
- cat> show what’s inside the document
- cd> change the directory
- mkdir> create a directory
- rm> remove a file
- rm -r > remove a directory
- nano> type the text in the directory
- whoami> who am I logged in as
- find -name> find  a file easier (leave “-name” and wrute the name of the file after that phrase)
- find -name *.txt> find every file that is “.txt”
- grep "name of the file" access.log> find how many entries were made into this file and from what IP
- ls -a > a list of directories available in the file
- ls -la > a list of what directory and when I accessed last

Operators learned:
- &> allows you to run commands in the background of your terminal
- &&> allows you to combine multiple commands together in one line of your terminal
- “>” > redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere 
- “>>” > This operator does the same function of the `>` operator but appends the output rather than replacing (meaning nothing is overwritten) 
