The SCAP Compliance Checker is an automated compliance scanning tool that leverages the
DISA Security Technical Implementation Guidelines (STIGs) and operating system (OS) specific
baselines to analyze and report on the security configuration of an information system. The tool
can be run locally on the host system to be scanned, or scans can be conducted across a network
from any machine on the domain. In either scanning environment, the following requirement
applies: The user conducting the scan must have administrative privileges on the machine to be
scanned. If the machine to be scanned is not hosting the tool, domain-level administrative
privileges (or individual local administrator accounts) are required to remotely scan other systems
on the network.

In order to download the SCAP Compliance Checker we can go to the `https://public.cyber.mil` website and then under that website you can go to `SRGs/STIGs` where under `Automation` you will find the `SCAP Compliance Checker`. Under the SCAP Compliance Checker we will find the different tools according to the Operating system that we are using. Such as `Windows, Unix, Ubuntu, Solaris, RHEL, etc.` They look like the following page. 

![scap](https://user-images.githubusercontent.com/93686063/231001890-cfdccdb5-9a40-4f11-8926-c99e889ec05e.JPG)

Since we are running our Scap Compliance Checker on a Windows machine, we will be downloading the SCC tool for Windows. `SCAP Compliance checker should always be used with administrative privileges`. Once we have downloaded the SCC tool, we will open the tool which will look like the following. 

![scap 1](https://user-images.githubusercontent.com/93686063/231002639-05e35ad2-a8da-462b-b4e8-ac8772ceb542.JPG)

We are going to need the latest benchmark so we will install and download the latest benchmark for the machine that we are trying to check for compliance.

![scap 2](https://user-images.githubusercontent.com/93686063/231002881-aaf58190-09a2-4bb9-90db-03a95369c018.JPG)

![scap 3](https://user-images.githubusercontent.com/93686063/231003122-928ae06f-317e-4e24-b272-54103836ecbe.JPG)

Once we have the latest benchmark for the compliance checker, then we will go under profile and check to see if we need to change it. THe profiles come in threee different types and they are as follows: 

  - ` Mac-1_Public` 
  - ` Mac-2_Sensitive`
  - ` Mac-3_Classified` 

![scap 4](https://user-images.githubusercontent.com/93686063/231003998-73b73cdf-45bd-4fb1-af49-a5baf1f4728f.JPG)


After we do all of this, we will hit the `Start Scan` 


![scapscan](https://user-images.githubusercontent.com/93686063/231004033-5245cd7e-50b2-4650-8f03-4e4bedc24fca.JPG)

Now on the SCAP Scan we always want to be above at least 80%, anything under 80% we will be in RED and Non Compliant. 

Our Scan for the Windows machine came out to be `95.71%`. Here is the following result which we can view as an HTML file. 


![sccresults](https://user-images.githubusercontent.com/93686063/231004442-f4f8ac74-5196-4386-bad3-8734d08e68b1.JPG)

Now not all of the results will be over 90%. Here is a result which was way below in RED. 


![sccresults1](https://user-images.githubusercontent.com/93686063/231004663-2d63d764-be21-443b-867a-cdfbe0abb470.JPG)

![sccresults2](https://user-images.githubusercontent.com/93686063/231006392-b825143d-b5a7-43ed-afa9-564451116462.JPG)

![class](https://user-images.githubusercontent.com/93686063/231007037-0c6f2871-3ecc-4c69-8b29-cc8e1b25cd2f.JPG)


If we get a result that is way below then we can automate some of the checks in order to be compliant. We can do that through a Local Group Policy. In order to do this, we can use the LGPO tool. So, we go into the folder where we have downloaded the LGPO tool and copy the location. We open Command Prompt under Administrator privileges. and cd into the LGPO Folder. 

![lgpo](https://user-images.githubusercontent.com/93686063/231007572-a3939008-601c-4403-b3ce-95bf34a4a30a.JPG)

LGPO.exe is a command-line utility that is designed to help automate management of Local Group 
Policy. It can import and apply settings from Registry Policy (Registry.pol) files, security templates, 
Advanced Auditing backup files, as well as from formatted “LGPO text” files and Policy Analyzer 
“.PolicyRules” XML files. 
It can export local policy to a GPO backup. It can export the contents of a 
Registry Policy file to the “LGPO text” format that can then be edited, and can build a Registry Policy file 
from an LGPO text file. (The syntax for LGPO text files is described later in this document.)
LGPO.exe has four command-line forms: for importing and applying settings to local policy – including to 
Multiple Local Group Policy Objects (MLGPO)1; for creating a GPO backup; for parsing a Registry Policy 
file and outputting “LGPO” text; for producing a Registry Policy file from an LGPO text file.

All output is written to LGPO.exe’s standard output, and all diagnostic and error information is written 
to its standard error. Both can be redirected to files using standard command shell operations. To 
support batch file use, LGPO.exe’s exit code is 0 on success and non-zero on any error.
LGPO.exe does not support Group Policy Preferences (GPP) at this time.

`In our case we used the /g path which imports settings from one or more group policy backups anywhere under the directory specified by path.` 

Once we do both the gpo for computers and users, we will use the command `gpupdate /force`

![update force](https://user-images.githubusercontent.com/93686063/231022848-2b32eab9-7f31-4a6c-be83-1a647c932b4f.JPG)

After we do all of this, the scc tool should now show a lot higher score most probably in the upper 90's and the rest of the compliance we can complete through the STIG viewer. 



