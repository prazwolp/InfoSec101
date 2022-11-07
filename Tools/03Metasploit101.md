
We will first look into Workspaces in Kali Linux. Workspaces are used to separate the work you are doing. When you are trying to exploit a machine, you would want to enumerate the machine. Enumeration basically means gathering as much information that you can using passive scanning or OSINT. 

Inside msfconsole, when you type $`workspace`, it will tell you which workspace you are in. If you want to know how many workspaces you have and which one you are working in you use $`workspace -v`. 

If you need to create a new workspace then you type $`workspace -a test`. The asterisk symbol is pointing to the workspace that you are currently in. If you need to delete a workspace then $`workspace -d name`. If you want to change the workspace then you just type $`workspace name`

We do this in order to keep track of all the work that we are doing without getting things too confusing between them. If we need to learn more about workspace $`help workspace`

 Inside msfconsole, we run an nmap scan as now we are trying to exploit another machine which is in the same network. In our case metasploitable3 which is a Windows Server 08. So we will run an nmap scan in order to find out more about the scan. Nmap is an aggressive scanner so we do not use Nmap in the wild unless we want to go to jail. DO NOT USE IT WITHOUT PERMISSION. 
 
 $` msf6 > db_nmap -p- -sV -O 10.0.2.6` (the -p stands for open ports, -sV stands for services running, -O stands for the Operating system, the IP address will be the one of your target machine, in our case the Windows Server 08 Metasploitable3) Use the Ip address of the machine you are trying to find out. Nmap takes a while for the results to come back, so be patient. 
 
 If we type $`hosts` or $`notes` or $`services` it will give us more information such as the os name, IP address and mac address of the target machine and the pupose as well, whether it is a workstation or a server. 
 
 Bruteforcing(SSH) Into Metasploitable3 with Kali Linux 
 
 Once we run an nmap we will get a list of services that are open and ports that are open. In the enumeration process when we find the information we can look for ways to bruteforce. When we ran nmap scan we can see in our particular Windows Server 08 that `ssh` port is open, so we will try and brute force the machine. We will now look for auxillary ssh scanners. 
 
 Our first step here is to look for aux ssh in msfconsole. We type $`msf6 > search type:aux ssh` We will get a list of scanners. We will find the one that will help us with our intent. In our case we are trying to brute force we will use the $`auxillary/scanner/ssh/ssh_login`. We either type $` use and the whole name or number in our case use 15`. If successful, we will see the scanner in red, which means we are inside it now. We will do $`show options` so that we can see what are the parameters that need to be set in order to get the job done. We will pay special attention to the $`yes` on $`Required` field. 
 
 0830 58:40 
 
 
 
 
 
 
 




