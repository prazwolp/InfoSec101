STIG stands for Security Technical Implementation Guidelines are a set of practices that are configuration standards developed by the Defense Information Systems Agency(DISA). They are designed to make device, hardware and software as secure as possible, safeguarding the DoD IT networks and systems. STIGs are updated every 90 days so that systems can be secured from new and upcoming threats. 

`For this example we will be Stigging a Windows 10 Server.`

We will start by first running a SCAP Compliance checker to see if there are any Cat 1 vulnerabilities that are in the system, these are the most important glaring vulnerabilities that may cause the system to loose data and be susceptible to attacks from the outside. Any vulnerability that is CAT 1 is a vulnerability and exploitation that can directly and immediately result in a loss of Confidentiality, Integrity and Availability. (CIA) 


First we will need to install the benchmarks from the DoD Cyber Exchange website (https://public.cyber.mil/stigs/downloads/). Once we have downloaded these we will open the SCAP Compliance Checker and on the Content Tab we will install the benchmarks. It looks like the following picture. 


![new1](https://user-images.githubusercontent.com/93686063/231167583-872110ed-62f6-409b-9b0c-7663a39d8c1a.JPG)

Some important things to look out for in the process is to make sure that we have the latest benchmarks and also the Profile. The profile will depend on the system that we are working with. They are divided into Public, Sensitive and Classified. Once we have put the checks in place. We will see the results and try and mitigate the open vulnerabilities in the system. 



![win](https://user-images.githubusercontent.com/93686063/231168386-c394a8c5-0624-4c99-9a59-b8cf049af7e7.JPG)

Anything above 90 is Green and we will now need to go in manually and make sure we can correct the Cat 1 vulnerabilities in place because those are the ones that leaves the system the most vulnerable to attacks. 

![win10](https://user-images.githubusercontent.com/93686063/231169216-278e4bac-8f0c-4730-9c5c-38d38ec6bf2c.JPG)

Once we open the STIG Viewer, we will now download the `Manual STIG` for Windows 10. 

![manualstig](https://user-images.githubusercontent.com/93686063/231170637-4d09b4a8-ff87-4639-a9c6-f4c9b3f759e2.JPG)


In some cases, there might not be a stig for scap with some applications, in those cases we need to manually check for vulnerabilities and not automate the whole process.

![manstig](https://user-images.githubusercontent.com/93686063/231171167-34a82b2b-bf43-4920-b3f4-deb22cdca4c1.JPG)

Now using the Manual STIG, we will create a checklist, we will select the `Create Checklist - Check Marked STIG(s)`. We are creating a baseline for how we want the system to be, and now we will bring the results file from the SCAP Compliance check and put it against the baseline to see where we are deficient. As soon as we create a new checklist, we will also save that checklist so we can use it against other systems that we will be checking. 

Now we will import the `XCCDF file` which is the result file from our previous SCAP scan to see how it matches with the checklist for the System to be compliant. 
The following is the result when we try to put our machine's result against the checklist. 

![result](https://user-images.githubusercontent.com/93686063/231173847-8d6a007c-aa56-4435-bea6-714db714744f.JPG)

First, we will focus on the CAT 1 vulnerabilities that we can mitigate as they are the most important ones. If we select a a vulnerability, it will tell us how we can mitigate the vulnerability and also a lot of other information such as how it is non compliant. We will focus on the `Vul ID V-220726` for this example. 

![vulid](https://user-images.githubusercontent.com/93686063/231183789-1402614c-c5ba-4add-a343-b019803fa1e4.JPG)

![sth](https://user-images.githubusercontent.com/93686063/231187247-ca262760-69ab-4710-ba48-7914a63eb06a.JPG)

`The Data Execution Prevention (DEP) must be configured to at least OptOut. DEP prevents harmful code from running in protected memory locations reserved for Windows and other programs.` 

![sth1](https://user-images.githubusercontent.com/93686063/231188811-19d9192e-7757-4963-b9d0-afeed6e6a206.JPG)

![sth3](https://user-images.githubusercontent.com/93686063/231189656-d6ebb733-9ae5-48c3-8854-376987945588.JPG)

Since we have corrected the issue, We will write in the comments section `Resolved as per Fixed Test` and on the Finding Details, we can outline `Not a finding. DEP is set to at least OptOut` and then go to Status and instead of `Open` pick ` Not a Finding`. This is how we manually removed a vulnerability that was out there. 


