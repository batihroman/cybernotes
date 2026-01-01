# Day 1 — WSL & Linux Basics
Date: 2025-12-31
Phase: 1 (Core Foundations)

## Goal of the Day
Understand what WSL is, how to work with Linux on Windows, and get comfortable navigating the terminal.

## Steps Completed Today
1. Installed WSL2 on Windows.
2. Installed Ubuntu as WSL distribution.
3. Created default Linux user (roman) with password.
4. Updated and upgraded packages:
   - Command: `sudo apt update && sudo apt upgrade -y`
5. Installed essential packages for Linux learning:
   - Command: `sudo apt install -y curl build-essential`
6. Configured Git globally:
   - `git config --global user.name`
   - `git config --global user.email`
7. Created a folder for notes and projects:
   - `mkdir ~/cybernotes`
   - `cd ~/cybernotes`

## Key Concepts to Remember
- **WSL (Windows Subsystem for Linux)** allows running Linux natively on Windows without a VM.
- **Linux terminal** is the main interface for commands; you don’t see feedback for passwords (security feature).
- **sudo** = run command as administrator/root.
- **apt** = package manager for Ubuntu; `update` refreshes package list, `upgrade` installs updates.
- **Git configuration** sets your identity for commits.
- **Directories**: `~` = your home folder; `mkdir` = make directory; `cd` = change directory.

## Commands to Practice
1. `pwd` — print current directory
2. `ls` — list files/folders
3. `cd <folder>` — navigate to folder
4. `mkdir <folder>` — create folder
5. `sudo apt update && sudo apt upgrade -y` — update system
6. `sudo apt install <package>` — install software
7. `git config --global user.name "YourName"` — set Git username
8. `git config --global user.email "email@example.com"` — set Git email

## Notes for My Journal
- WSL allows using Linux tools without leaving Windows.
- Linux terminal navigation is essential for all labs.
- Git will be used to track projects and labs.
- CyberNotes folder = central place to store notes and screenshots.

## Next Steps / Homework
- Open Ubuntu in WSL: `wsl` or `Ubuntu` from Start menu.
- Practice basic commands: `pwd`, `ls`, `cd`.
- Make 2–3 nested directories inside `~/cybernotes` and navigate them.
- Take a screenshot of terminal with commands executed and save in `~/cybernotes/screenshots`.


