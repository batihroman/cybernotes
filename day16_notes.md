Day 16: Cybersecurity 101 | Windows PowerShell.

What I did today: 
- Completed a THM room "Windows PowerShell" 
- Learned most of the basic command to navigate, track the network, work with files and do a real-time system analysis.
- Explored the Powershell and understood how it can be useful in the cybersecurity.

Commands learned today:

BASICS

- Get-Commad : info about commads that can be executed.
- Get-Command -CommandType “exemple Function” : Commands only of the type “Function”.
- Get-Help “Some Command” : Get info about this command.
- Get-Alias : Get shortened names for commands.
- Find-Module : To search for new cmdlets to add to the Powershell.
- Find-Module -Property “pattern” : Find the exaxt module thaat you want to add.
- Install-Module -Name “randomname” : Install the given module.

NAVIGATING THE FILE SYSTEM AND FILES

- Get-ChildItem (dir or ls) : To view the context of the directory.
- Set-Location (cd) : To go to the different directory.
- New-Item : To create a new item. (-Path “.\some\directory to specify where to add this file to).
- Remove-Item (rmdir or del) : Remove the directory. (-Path “.\some\directory to remove exact directory).
- Copy-Item (copy) : Copy the item. (same pattern with -Path applies).
- Move-Item (move) : To move the item. (same pattern with -Path applies).
- Get-Conatent (cat) : To display the content of the file. (same pattern with -Path applies).

PIPING, FILTERING, SORTING

- Use | to pipe (combine) two command together. (Get-ChildItem | Where-Object -Property "Extension" -eq ".txt")
- Extentions -eq : equal to/ -ne : not equal / -gt : greater than / -ge : greater than or equal to / -lt : less than / -le : less than or equal to.
- Select-Object + some property : to select specific properties form objects.
- Select-String (grep) :  searches for text patterns within files. (same pattern with -Path applies).

SYSTEM AND NETWORK INFO

- Get-ComputerInfo : retrieves comprehensive system information, including operating system information, hardware specifications, BIOS details, and more.
- Get-LocalUser :  lists all the local user accounts on the system.
- Get-NetIPConfiguration : detailed information about the network interfaces on the system.
- Get-NetIPAddress :  shows details for all IP addresses configured on the system, including those that are not currently active.

SYSTEM ANALYSIS

- Get-Process : a detailed view of all currently running processes.
- Get-Service : the retrieval of information about the status of services on the machine.
- Get-NetTCPConnection : displays current TCP connections, giving insights into both local and remote endpoints.
- Get-FileHash : generates a file hashes.

SCRIPTING

- Invoke-Command : executes command on remote machines.
