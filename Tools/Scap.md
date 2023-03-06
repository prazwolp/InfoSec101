![scap](https://user-images.githubusercontent.com/93686063/223177362-33aece2c-ea86-40b9-a1be-cc99b813ec9b.JPG)

The Information Systems Security Manager (ISSM) is responsible for preparing an organization's Information System for authorization under the NISP. The following steps need to be performed in order to make sure that the system is authorized to carry out business functions under NISP. 

![authorization under NISP](https://user-images.githubusercontent.com/93686063/223205351-18d47943-f42f-4222-9416-fd68349be966.JPG)

In order to do a self-assessment, there are two tools. First one is the SCAP Compliance checker and the other one is the the STIG viewer. We will first go through the SCAP Compliance checker. 

$`SCAP (Security Content Automation Protocol)` 

The SCAP Compliance checker is an automated vulnerability scanning tool, it leverages the Defense Information Systems Agency (DISA), Security Technical Implementation Guides(STIG) and Operating system specific baselines to analyze and report on the security configuration of an information system. Once you install The SCAP Compliance checker, you open it and you have to selct the appropriate baseline for the system that is to be scanned. 

![scapchecker](https://user-images.githubusercontent.com/93686063/223216860-6e0b08aa-a928-4021-a3f3-f87d7052c15d.JPG)

`Edit-> Content and Options`. 

![scapedit](https://user-images.githubusercontent.com/93686063/223217301-92068d7b-b4aa-4e18-a8c6-f3b2563c4bae.JPG)

Now you will have to do `Install SCAP Content` 

![installscap](https://user-images.githubusercontent.com/93686063/223217867-c8c4afeb-28fa-4c66-9960-55e3034dc10e.JPG)

In the Window that appears you will now navigate to the `Benchmark` that you previously downloaded. 


![scapinstall](https://user-images.githubusercontent.com/93686063/223218176-699806c8-cdbb-4e54-9f39-da12e874281a.JPG)

You will always select the latest version, it is generally the last one installed and has the latest date. 

![classified](https://user-images.githubusercontent.com/93686063/223218480-e3eaeb5d-4768-4f65-bc36-b7c78ac9ee32.JPG)

Once we do that we nede to check box for the appropriate baseline that corresponds to the system being scanned. The Scan Profile should always be "MAC-3 Classified". 

You should always have the button on Local Computer and hit `Analyze Selected Computer` to initiate the scan. 

![baseline](https://user-images.githubusercontent.com/93686063/223207672-f545c05d-42e8-4817-940e-8a4cf39ce4a7.JPG)

Once the scan is complete, you will selct the `Results` tab. To access the results, you will hit `Open Results Directory`. Double click on the folder with the most recent date. You will open the folder called `SCAP` and double click on the largest file which will be titled `All Settings Report`. 

![largest](https://user-images.githubusercontent.com/93686063/223219167-6847fc91-ff3f-4428-a16c-55b29f6951c4.JPG)

If you were to open the smaller file, you will get the `non-compliance report`. This is a report which shows open vulnerabilities. 

![report](https://user-images.githubusercontent.com/93686063/223219375-aeddc535-7c53-4929-a746-6ef822e97072.JPG)

Now we copy the folder to Desktop, so we can easily access it. We click on the `XML` folder and copy the `XCCDF` file. 


Once we complete this part, we initiate the scan by clicking on `Analyse Selected Computer(s)`. After the scan is completed we need to see the results of the scan for which we will go to `Results->Open Results Directory`. This is will open the Scan Results Directory. When we get to the directory we will need to look out for the `XML` file containing `XCCDF`. This is the file that we will be importing to the `STIG Viewer` to analyze the compliance state of the machine. Once we have the `XCCDF` file, we will open the STIG Viewer in order to see the report. 


