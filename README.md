# TryHackMe - Tardigrade
![Room Logo](./img/logo.png)  
Room Link => [Tardigrade](https://tryhackme.com/room/tardigrade)

### Task 1 (Connect to the machine via SSH)
1. What is the server's OS version?  
It's visible in the login message.  
`Ubuntu **.**.* ***`

### Task 2 (Investigating the giorgio account)  
1. What's the most interesting file you found in giorgio's home directory?  
execute the command `ls -la` and you will find a file with suid bits set added in it. Running `ls` command wont work and you will know in a second.