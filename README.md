# TryHackMe - Tardigrade
![Room Logo](./img/logo.png)  
Room Link => [Tardigrade](https://tryhackme.com/room/tardigrade)

### Task 1 (Connect to the machine via SSH)
1. What is the server's OS version?  
It's visible in the login message.  
`Ubuntu **.**.* ***`

### Task 2 (Investigating the giorgio account)  
1. What's the most interesting file you found in giorgio's home directory?  
Execute the command `ls -la` and you will find a file with suid bits set added in it. Name of that file is the answer fo rthis one. Running `ls` command wont work and you will know why in a second.

2. Another file that can be found in every user's home directory is the .bashrc file. Can you check if you can find something interesting in giorgio's .bashrc?  
`cat .bashrc` and go through all the `alias` command's and you will find one where ls is set to an alias for a reverse shell command.