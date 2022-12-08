Nessus is a remote security scanning tool developed by Tenebale Inc that scans a computer and raises an alerts if it discovers any vulnerabilities that malicious hackers could use to gain access to any computer you have connected to a network. It is a great tool that help keeps their domains free of the easy vulnerabilities that hackers and viruses commonly look to exploit. 

Nessus is an open-source vulnerability scanner that uses the Common Vulnerabilities and Exposure architecture for easy cross-linking between compliant security tools. It is one of the many vulneraility scanners used during vulnerability assessments and penetration testing engagements, including malicious attacks. 

Nessus works by testing each port on a computer, determining what service it is running, and then testing this service to make sure there are no vulnerbilities in it that could be used by a hacker to carry out a malicious attack. 
Nessus can scan these vulnerabilities and exposures:

    Vulnerabilities that could allow unauthorized control or access to sensitive data on a system
    Misconfiguration (e.g. open mail relay)
    Denials of service (Dos) vulnerabilities
    Default passwords, a few common passwords, and blank/absent passwords on some system accounts
 
 
 
 We will start by downloading Nessus through our firefox browser in Kali Linux. We will be downloading the `$Nessus essetials` from Tebable Website. Once we click on Nessus Essetials, we will go to the `$ Register for an Activation Code`. Here we will put our names and email in order to get the code. Once we get the code we will be downloading the `$Nessus amd64 Debian 8.15 for Kali Linux` We will be downloading through the command prompt. We will cd into the downloads folder. `$ cd Downloads` Once we are inside the Downloads folder, we will type in `$ dpkg --install N(tab)` this will self populate with the download file that we have. Once we get this running, we will go back to our terminal and type in `$ service nessusd start` The 'd' is for nessus Debian that we have installed. 

After this we will go to a browser in Kali Linux and type in `$ https://localhost:8834`. That is the port number being used. Once we do this we click on `$Nessus Essentials` which will take us to the login page, since we already have the activation code, we will skip the first step and use the second one. We will create a username and password which we can remember. `$kali - toor` in ours case. It will start downloading plugins. 
