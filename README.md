# TryHackMe - Tardigrade
![Room Logo](./img/logo.png)  
Room Link => [Tardigrade](https://tryhackme.com/room/tardigrade)

### Task 1 (Connect to the machine via SSH)
1. What is the server's OS version?  
It's visible in the login message.  
`Ubuntu **.**.* ***`

### Task 2 (Investigating the giorgio account)  
1. What's the most interesting file you found in giorgio's home directory?  
>Execute the command `ls -la` and you will find a file with suid bit set added in it. Name of that file is the answer fo rthis one. Running `ls` command wont work and you will know why in a second.

2. Another file that can be found in every user's home directory is the .bashrc file. Can you check if you can find something interesting in giorgio's .bashrc?  
>`cat .bashrc` and go through all the `alias` command's and you will find one where ls is set to an alias for a reverse shell command.  

3. Did you find anything interesting about scheduled tasks?  
>`crontab -l` will show you a task which is again a reverse shell command.  

### Task 3 (Dirty Wordlist Revisited)  
1. What is the flag?  
>Read the paragraph for the flag.

### Task 4 (Investigating the root account)  
**Let's switch to root user by using the `.bad_bash`**  
**Execute the command `./.bad_bash -p` and you will become the root user.**  
**I started solving this from last question to first because the first question asks for an error message after login which i didn'nt get.**

3. Can you find out how the suspicious command has been implemented ?  
>Switch to root directory and read the `.bashrc` file. You will find a netcat command for reverse shell.

2. What command was displayed ?  
>Netcat command found in `.bashrc`.

1. A few moments after logging on to the root account, you find an error message in your terminal. What does it say ?  
>Execute the netcat command you found and you will have the answer for this one.  

### Task 5 (Investigating the system)
1. This specific persistence mechanism is directly tied to something (or someone?) already present in fresh Linux installs and may be abused and/or manipulated to fit an adversary's goals. What's its name ? What is the last persistence mechanism ?  
>The word `someone` in the question made me think if there is an unusual user present so i read the `passwd` file and found that there is infact an unusual user with a directory and a login shell. You can do `cat /etc/passwd | grep bash` and get the username.

### Task 6 (Final Thoughts)  
1. What is the nugget ?  
>Go inside the directory of the new user. `ls -la` and you will see a hidden file. `cat` that file to get your flag.