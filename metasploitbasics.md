MetaSploit Framework 

MetaSploit is a Ruby based modular penetration testing platform that enables you to write, test & execute exploit code. Metasploit contains a set of tools that you can use to 

- test security vulnerabilities

- enumerate networks ( process that involves gathering information about a network such as hosts, connected devices along with usernames, group info and related data) 

In order to start metasploit in Linux, the following commands need to be entered first. 

$ `service postgresql start` ( to start the database) 

$ `service postgresql status` (to check the status of the database wether it has started or not) 

$ `msfdb init` (this is to initialize the database) 

$ `msfconsole` (this starts the msfconsole) 

If all the commands are correct then we will get to the following command line 

$`msf6 >`

In order to search for exploits, we need to use the search command. If we need to learn more about how to use the search options we can use the $`help search` command. This will give us examples as to how to search for things. 

