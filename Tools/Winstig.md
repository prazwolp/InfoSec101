STIG stands for Security Technical Implementation Guidelines are a set of practices that are configuration standards developed by the Defense Information Systems Agency(DISA). They are designed to make device, hardware and software as secure as possible, safeguarding the DoD IT networks and systems. STIGs are updated every 90 days so that systems can be secured from new and upcoming threats. 

`For this example we will be Stigging a Windows 10 Server.`

We will start by first running a SCAP Compliance checker to see if there are any Cat 1 vulnerabilities that are in the system, these are the most important glaring vulnerabilities that may cause the system to loose data and be susceptible to attacks from the outside. Any vulnerability that is CAT 1 is a vulnerability and exploitation that can directly and immediately result in a loss of Confidentiality, Integrity and Availability. (CIA) 


First we will need to install the benchmarks from the DoD Cyber Exchange website (https://public.cyber.mil/stigs/downloads/). Once we have downloaded these we will open the SCAP Compliance Checker and on the Content Tab we will install the benchmarks. It looks like the following picture. 


![new1](https://user-images.githubusercontent.com/93686063/231167583-872110ed-62f6-409b-9b0c-7663a39d8c1a.JPG)

Some important things to look out for in the process is to make sure that we have the latest benchmarks and also the Profile. The profile will depend on the system that we are working with. They are divided into Public, Sensitive and Classified. Once we have put the checks in place. We will see the results and try and mitigate the open vulnerabilities in the system. 



![win](https://user-images.githubusercontent.com/93686063/231168386-c394a8c5-0624-4c99-9a59-b8cf049af7e7.JPG)

Anything above 90 is Green and we will now need to go in manually and make sure we can correct the Cat 1 vulnerabilities in place because those are the ones that leaves the system the most vulnerable to attacks. 

![win10](https://user-images.githubusercontent.com/93686063/231169216-278e4bac-8f0c-4730-9c5c-38d38ec6bf2c.JPG)

