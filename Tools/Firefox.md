Firefox is a popular browser that is used to access the Internet. For this particular check we will run the SCAP Compliance checker we will see if the browser is fit to use and it has no vulnerabilities that will affect the Confidentiality, Intergrity and Avaliability. 

![mf](https://user-images.githubusercontent.com/93686063/231775409-6d301a21-bb8a-4656-85b9-45a9aa36abf4.JPG)

![mf1](https://user-images.githubusercontent.com/93686063/231777289-a8e259e5-679b-4500-a886-54301ffa992a.JPG)

Since there are a lot of errors that we need to fix, we will be using the LGPO tool which automates a lot of these processes. 

`LGPO.exe is a command-line utility that is designed to help automate management of Local Group Policy. It can import and apply settings from Registry Policy(Registry.pol) files, security templates, Advanced Auditing backup files, as well as formatted "LGPO text" files and Policy Analyzer ".PolicyRules"XML files.` 

We will now go to the DoD Cyber Exchange website and download the Group Policy Objects(GPOs). The latest ones that we have are from January 2023.

![gpo](https://user-images.githubusercontent.com/93686063/231779553-acd4abf7-01a6-4d56-bd73-c3d2efab4e01.JPG)

We will first copy the `.admx` and `.adml` files in our C:\Windows\PolicyDefinitions. 

`Before we run the LGPO tool for Firefox, we need to make sure that we copy the Administrative Templates in Group Policy. ADMX files are XML text files that describe what you see under Computer Configuration\Policies\Administrative Templates and User Configuration in Group Policy Editor. Once these files are stored mostly under Policy Definitions in the Windows Folder, the only time they are read or considered are when you are editing GPOs in GP Editor. When you expand the Administrative Template node, and you see all of those folders, sub-folders and policy items those correspond to GP Editor reading each ADMX File it finds.` 


![gpo1](https://user-images.githubusercontent.com/93686063/231783250-9ca72f45-d19b-4ad7-b2e3-8837f5ff01c2.JPG)

We will also need to copy the `.adml` files which are located in the en-US folder. 


![gpo2](https://user-images.githubusercontent.com/93686063/231783707-fc45fdea-e613-4a5e-97f3-1a0a98c841a3.JPG)


Once we are inside the LGPO folder in an elevated Command prompt, we will use the LGPO.exe command. The LGPO.exe applies the contents of the supplied input files to local policy. We will be using the `/g path` which `imports the settings from one or more Group Policy backups anywhere under the directory specified by path`. 

![gpo3](https://user-images.githubusercontent.com/93686063/231785524-faaca7c0-f844-4c13-ab45-76c01a3005ad.JPG)

We will get the following result, now that we have the following result, we will do a `gpupdate /force` in order to update the policies. 

![gpo4](https://user-images.githubusercontent.com/93686063/231786713-ea3f8a42-5294-4db1-a3ab-274d0f1784fd.JPG)

Now that we have updated the policies and used the LGPO tools, we can see a different result and a far better result for the same application. We are well above GREEN on the compliance and we can now run the Stig viewer to see if we can make any changes manually. 

![gpo5](https://user-images.githubusercontent.com/93686063/231787214-fdedb6f6-79ee-4434-ab71-b0bc825baa74.JPG)

![image](https://user-images.githubusercontent.com/93686063/231787484-0aaca316-4d0e-4d64-ad15-ef5a8e523dfe.png)

First we will need to import the STIG for Firefox and make sure we check that Stig and create a checklist and save the checklist so it only checkes for that particular application and not all of the ones we have on the STIG panel. 

![ff](https://user-images.githubusercontent.com/93686063/231816765-a6a94578-8c17-4ded-a157-a8dd31e8dbda.JPG)

After we have created the checklist to check our own application in our machine, we will import the `XCCDF` file from our latest results in the SCAP Compliance Checker. This is what the results look like. 

![fr](https://user-images.githubusercontent.com/93686063/231817551-b524e9d9-acab-49d6-8ff7-e03874fa1838.JPG)


Now for example we cannot be compliant on the one CAT II Open Vulnerability with `Vul ID -> V-251577` which according to the Rule Title is `Firefox must be configured so that DNS over HTTPS is disabled.` We will need to document this in the document (POA&M). 

`POA&M stands for Plan of Actions and Milestones`. 

` The purpose of the POA&M is to assist organizations in identifying, assessing, prioritizing, and monitoring the progress of corrective efforts for security weaknesses/deficiences/vulnerabilities found in programs and systems.` 

`The POA&M is created as part of the 5th Step (Authorize System) in the 6-step Risk Management Framework(RMF) process and when common controls have been determined, through independent assessments, to be less than effective. The POA&M is maintained as part of the Security Authorization Package(formerly known as the Certification and Accredition, or C&A package.)` 

Here is the link in order to know more about a POA&M and Template to document the vulnerability which cannot be fixed right now with the Firefox Browser. The website also lets you download a POA&M template in order to fill one out. 

(https://www.cdse.edu/Portals/124/Documents/jobaids/cyber/CDSE_POAM_Final_Job_Aid.pdf)


Below is an example of a POA&M we filled out in order to address the issue that we are not able to fix at this point. 

![po](https://user-images.githubusercontent.com/93686063/232060988-3636804e-06b1-4b4f-a0d9-55f8336131bb.JPG)

POA&M's are created as part 5 (Authorize) in the 6 step Risk Management Framework process. POA&M facilitates a disciplines and structured approach to mitigating risks in accordance with the priorities of the ISO. It is maintained throughout the system life cycle. 

Here are a few things we filled out for the particular vulnerability which is still open. 

  - `Item Identifier` is a unique identifier used to track and corelate weakness that are ongoing throughout quarterly submissions within the organization. 
  
  - `Weakness or Deficiency` This could be any program or system level information security vulnerability that poses an unacceptable risk of compromising CIA, in        our case it would be that `if we do not correct the security control CM-7, then there is an increase in risk to the platform by providing additional attack          vectors`. One can also just use the Rule Title from the Stig Viewer where for this particular control we can see `Firefox must be configured so that DNS over        HTTPS is disabled`.  
  
  - `Security Control` are the controls that are listed in the NIST SP 800-53 and they directly relate to the weakness identified in the Weakness or Deficiency          column. `In our case, the security contol that is identified as a weakness is the NIST SP 800-53:: CM -7` CM is a set of Control Families that are listed in        the document NIST SP 800-53. `CM Stands for Configuration Management` 
  
  - `Point of Contact` could be an organization or title of the position within the organization that is responsible for mitigating the weakness. 
  
  - `Resources required` is the estimated funding and or manpower resources required for mitigating the weakness. In our case, we will just put down `Engineers          needed`. 
  
  - `Scheduled Completion Date` is based on a realistic estimate of the amount of time it will take to procure/allocate the resources required for the corrective        action and implement/test the corrective action. In our case we put in `Q3 2023`. `ALWAYS ENTER EITHER THE ESTIMATED COMPLETION DATE OR N/A IF THE RISK IS          ACCEPTED`. If a security weakness is resolved before or after the originally scheduled completion date, put the actual completion date in the Status Field. 
  
  - `Milestones with Completion Date` are specific high level steps to be executed in mitigating the weakness and the estimated completion date for each step. 
  
  - `Changes to Milestones` is the new estimated completion date for a milestone and the reason for the change. 
  
  - `Weakness or Deficiency Identified by` is the source of the weakness, the reviewing agency or organization and the date that weakness was identified. The source      of the weakness could be Security Control assessment, Penetration Test, IG audit, Certification testing. 
  
  - `Risk Level` is the ranking that determines the impact of a vulnerability, if exploited to the system, data, and/or program. The risk levels could be Low,            Medium or High. In our case the contol is a Cat II issue so we will just select `Medium`. 
  - 
