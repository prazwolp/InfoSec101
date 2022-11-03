The first thing you do in terms of enumeration is using tools like NMap to find out what ports are open and what OS the system is using and what vulnerabilities we can find in order to exploit the system. Once we find the OS or the browser whose exploit is available in msfconsole we go ahead and start the process. 
The things we need to look for when we first find how we are going to exploit the system are the following things: 

$`RHOST -- This is the victim machine` 

$`LHOST -- This is the machine that we are attacking from, in our case the kali Linux` 

$`RPORT -- The target port` 

When we do options after we use any of the exploit, then if we do options we can see the parameters that are required. We must give the machine the parameters that say "required" 

The following steps should be followed in order to exploit a system. 

1. Search for the type of exploit that you will need. The examples for the way to look for exploits is as follows: 

$` search cve:2009 type:exploit platform:linux ` In this search line, we are looking for a CVE for 2009, the type we are looking for is exploit and the platform that we are looking the exploit for is Linux



