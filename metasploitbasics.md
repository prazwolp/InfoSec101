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

In order to use the search command first we need to understand about exploits. 

CVE stands for Common Vulnerabilites and Exposures. CVE is a glossary that classifies vulnerabilities. The glossary analyzes vulnerabilities and then uses the Common Vulnerability Scoring System (CVSS) to evaluate the threat level of a vulnerability. A CVE Score is often used for prioritizing the security of vulnerability. 

For example the Eternal Blue exploit is CVE 2017-0143 to CVE 2017-0148 are a family of cricital vulnerabilities in Microsoft SMBv1 server used in Windows 7, Windows Server 2008, Windows XP and even Windows 10 running on port 445. 

EternalBlue itself concerns CVE-2017-0144, is a flaw that allows remote attackers to execute arbitraty code on a target system by sending specially crafted messages to the SMBv1 server. Even Though the patch from Windows was released, many have still not been patched. Below are the list of versions which still remain unpatched at the time of writing and the OS's that are vulnerable to Eternal Blue. 

![eternalblue](https://user-images.githubusercontent.com/93686063/199555403-98697072-1420-4b28-b49f-dd87ebb9ae12.JPG)

CWE stands for Common Weakness Enumeration, it refers to the type of softwarde weaknesses, rather than specific instances of vulnerabilities within products or systems. CWE works to stop vulnerabilities and bugs by educating developers on building better products that are not susceptible to exploitation. Programmers use CWE as a resource while writing code to prevent vulnerabilities during the development process. SOAR tools used CWE's to build policies and workflows to automate remediation. Some examples of CWE are as follows: 

$` CWE 787 - out of bounds writing `
$` CWE 79 - improperly neutralizing input when generating web pages (cross-site scripting) `
$` CWE 89 - improperly neutralizing special elements in the SQL command (SQL injection) `
