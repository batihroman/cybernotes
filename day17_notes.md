Day 17. Linux Shells.

<Types of Linux Shells>
- To view the shell you are using: echo $SHELL.
- To see the shells preinstalled on a Linux system: cat /etc/shells.
- To switch between the shells: type the name of the shell you want to switch to. 
- If you want to permanently change your default shell: chsh -s /usr/bin/zsh

Bourne Again Shell:
- Default for most Linux distributions.
- An enhanced replacement for shells like sh, ksh, csh and absorbed their best qualities with adding some of its own.
- Bash is a widely used shell with scripting capabilities.
- It offers a tab completion feature, which means if you are in the middle of completing a command, you can press the tab key on your keyboard. It will automatically complete the command based on a possible match or give you multiple suggestions for completing it.
- Bash keeps a history file and logs all of your commands. You can use the up and down arrow keys to use the previous commands without typing them again. You can also type history to display all your previous commands.

Friendly Interactive Shell:
- It offers a very simple syntax, which is feasible for beginner users.
- Unlike bash, it has auto spell correction for the commands you write.
- You can customize the command prompt with some cool themes using fish.
- The syntax highlighting feature of fish colors different parts of a command based on their roles, which can improve the readability of commands. It also helps us to spot errors with their unique colors.
- Fish also provides scripting, tab completion, and command history functionality like the shells mentioned in this task.

Z Shell:
- Zsh provides advanced tab completion and is also capable of writing scripts.
- Just like fish, it also provides auto spell correction for the commands.
- It offers extensive customization that may make it slower than other shells.
- It also provides tab completion, command history functionality, and several other features.

<Shell Scripting and Components>
Helps to automate and perform tasks by scripting a set of commands.

- To start a script use a nano command, then a script has to start with "#!/bin/shell you are on"
- Complete the script using CTRL+X, then Y, and then ENTER.
- To give permissions to the script use chmod +x nameofthescript.
- To execute the script use ./name of the script.

Loop Script:
A repetative script that helps you perform many tasks at once in a loop.
The first line has the variable i that will iterate from 1 to 10 and execute the below code every time. do indicates the start of the loop code, and done indicates the end.\
The for loop will take each number in the brackets and assign it to the variable i in each iteration. The echo $i will display this variable’s value every iteration.

Conditional statesments:
They help you execute a specific code only when a condition is satisfied; otherwise, you can execute another code.
"Example: echo "please do something:"
read name
if [ "$name" = "something" ]; then 
echo "something"
else
echo "nope"
fi"

Comments:
You can add comments to the script using #.
They are essential part of every script.

<The Locker Script>

