![scap](https://user-images.githubusercontent.com/93686063/223177362-33aece2c-ea86-40b9-a1be-cc99b813ec9b.JPG)

The Information Systems Security Manager (ISSM) is responsible for preparing an organization's Information System for authorization under the NISP. The following steps need to be performed in order to make sure that the system is authorized to carry out business functions under NISP. 

![authorization under NISP](https://user-images.githubusercontent.com/93686063/223205351-18d47943-f42f-4222-9416-fd68349be966.JPG)

In order to do a self-assessment, there are two tools. First one is the SCAP Compliance checker and the other one is the the STIG viewer. We will first go through the SCAP Compliance checker. 

$`SCAP (Security Content Automation Protocol)` 

The SCAP Compliance checker is an automated vulnerability scanning tool, it leverages the Defense Information Systems Agency (DISA), Security Technical Implementation Guides(STIG) and Operating system specific baselines to analyze and report on the security configuration of an information system. Once you install The SCAP Compliance checker, you open it and you have to selct the appropriate baseline for the system that is to be scanned, which can be done by clicking on `Edit-> Content and Options`. Once we do that we nede to check box for the appropriate baseline that corresponds to the system being scanned. The Scan Profile should always be "MAC-3 Classified". 



![scapchecker](https://user-images.githubusercontent.com/93686063/223216860-6e0b08aa-a928-4021-a3f3-f87d7052c15d.JPG)

![baseline](https://user-images.githubusercontent.com/93686063/223207672-f545c05d-42e8-4817-940e-8a4cf39ce4a7.JPG)

Once we complete this part, we initiate the scan by clicking on `Analyse Selected Computer(s)`. After the scan is completed we need to see the results of the scan for which we will go to `Results->Open Results Directory`. This is will open the Scan Results Directory. When we get to the directory we will need to look out for the `XML` file containing `XCCDF`. This is the file that we will be importing to the `STIG Viewer` to analyze the compliance state of the machine. 

