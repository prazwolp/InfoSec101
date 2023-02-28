`Linux Privilege Escalation` 

 We will be using TryHackme for this course. The room that we will be using will be the "linuxprivescarena". The link for this room is "https://tryhackme.com/room/linuxprivescarena". In this room we will ssh into a linux and see how we can escalate privileges once we have access to the linux machine. 
 
 We will also be using a Github Repo in order to get resource that we will need in order to escalate the privileges in the machine. The link is as follows: 
 "https://github.com/Gr1mmie/Linux-Privilege-Escalation-Resources"
 
 `Kernel Exploits Overview` 
  ![kernel](https://user-images.githubusercontent.com/93686063/221947968-acf303b0-14ae-4d0b-a849-e25db5e1a9a8.JPG)
  
  `What is a Kernel?` 
  
  Kernel lives between the applications and the hardware. It facilitates the interaction between hardware and software components works like a translator. There   is a github by the name of Kernel Exploits (https://github.com/lucyoa/kernel-exploits). 
  
  $`Dirty Cow Kernel Exploit` 
  
  When looking for exploits online for any machine that we have, we need to look for an exploit which will give us root access, some exploits do not really get   us complete access. For example, a race condition privilege escalation attack would be a good exploit to look for. A race condition exploit for example, 
  before allowing someone to log in, a security system first receives their username and password and then checks it against a database before allowing access. 
  Attackers can exploit this fact by interfering with processes to access secure areas and content in what's known as a race condition attack. 
  
  For the 

 
 
