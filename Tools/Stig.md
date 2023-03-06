`STIG Viewer` 

The Security Technical Implementation Guide (STIG) viewer is an unclassified, non-PKI controlled tool which can be downloaded from the DISA's IASE website. It is a java based application and does not require an installation, thus it runs as a Java Applet. It is used with the SCAP Compliance Checker, it allows you to view compliance status of the system's security settings. The Stig viewer looks like the following. 


![stig viewer](https://user-images.githubusercontent.com/93686063/223211830-b01357a6-0978-4fd0-ae78-a296846ad0a2.JPG)

After you get the STIG Viewer, you will need to download STIGS. STIGS are the Security Technical Implementation Guides, configuration based on DoD policy and security controls that contain technical guidance to lock down information systems and software that might otherwise be vulnerable to a malicious computer attack. 

In order to get the STIG, first we need to make sure we have the correct OS in order to access the STIG's. Always look for the latest version of the STIG. Download the correct STIG. 

![stig1](https://user-images.githubusercontent.com/93686063/223220332-b2c67dd2-8154-46d2-853e-9aab0f6b82ab.JPG)



So we open the STIG Viewer and select the `File` tab, and select `Import STIG`. Here, we are opening the `XCCDF` file that we have as a baseline and not the file that we just got from the SCAP Scan. 
![xccdf](https://user-images.githubusercontent.com/93686063/223220761-91ce6a0e-804b-4dfb-86d9-c32b8b6ccc99.JPG)

We now select the imported file checklist button. 

![create](https://user-images.githubusercontent.com/93686063/223221020-efe6e7b1-19ae-4904-849a-36a2c98e861d.JPG)

This is when you import the file that you got from the Scan earlier. Select `Import` and hit `XCCDF Results File`. 
![xccdfr](https://user-images.githubusercontent.com/93686063/223221321-1dda01f7-3d06-404b-b113-f486215a42c5.JPG)


![xccdf2](https://user-images.githubusercontent.com/93686063/223221495-ec81d01e-00f6-4e8a-9b89-ba1d62e3d4ee.JPG)


