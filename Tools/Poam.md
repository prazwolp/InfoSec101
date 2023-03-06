Below is an example of the POA&M. POA&M stands for `Plan of Action and Milestones` 

![poam](https://user-images.githubusercontent.com/93686063/223229649-6105e4b0-76c3-457a-a3a5-fc30fe5d16bc.JPG)

Below are the purposes of POA&M. 

![purposepoam](https://user-images.githubusercontent.com/93686063/223229822-4f4f8eb6-63a6-4314-91ac-68fca67d1e05.JPG)

For example, listings in the POA&M should be unmitigated vulnerabilities, examples include an outdated patch, an incorrect version of Java, or a misconfigured seucrity setting. Until these listings are mitigated, their status is recorded in the open findings section of the POA&M and continuously monitored. 

There will be two tabs. One will be active items and the vulnerabilties that have been mitigated will be in the `Completed` tabs. In the top block, you will find space to list system specific, or organization specific information. You will see that in the last block, IS type, you could select enclave type. For `UID`, unique identifier, this is a number unique to your organization, your organization's schema or naming system. 

The `Weakness or Deficiency` tab represents any program level or system level deficiency that poses an unacceptable risk or compromise in confidentiality, integrity of availability of the system. 

The ` Security Control` tab list the security controls from NIST Special Publication 800-53 and directly relates them to the weakness identified or deficiency columns. Enter the security control that corelates with the weakness or deficiency. 

The `POC` tab you enter the title of a position within an organizaton that is responsible for mitigating the weakness. 

The `Resources Required` tab include the total funding requirements of the security solution, also note if the resources are current, new or re-allocated. 

The `Scheduled Completion Date` is a date based on the realistic estimate of the amount of time needed to procure and allocate the resources required for corrective action. Enter NA if the risk is going to be accepted. 

The `Milestones with Completion Dates`, you will enter the specific high levels to be executed in mitigating the weaknesses and the estimated completion date for each step. 

The `Change to Milestones` tab, you enter new estimated completion dates for milestones and reason for the change. If date not met, enter new date and the reason why the new date was not met. 

The `Weakness/Deficiency Identified by` tab list the source of the weakness plus the reviewing agency, the organization and the date that the weakness was identified. 

The `Risk Level(Low/Med/High)` is if there is high risk, there is a catastrophic effect on the system of operations. If the risk is medium, there is a severe adverse risk to the system or operations, and low means there is a risk of limited adverse effect to the system or operations. 

The `Estimated Cost` tab is the total cost which may include man hours, by adding up all the individual estimated costs of correcting each weakness or deficiency. 

The `Status` tab which notes the state of the weakness as in completed, ongoing, delayed, planned or accepted. 

The `Comments` tab, you enter explanations for the delay or change in a milestone or a scheduled completion date, or identify obstacles or challenges that are non-funding related, such as lack of personnel or expertise related to that personnel. 



Below is an example as to how to fill out a POA&M form. There is an open vulnerability of V-14236: UAC - User Elevation Prompt. The User Account Control is not currently enabled and does not prompt the user for credentials when requiring elevation. This is due to the legacy software that is pending update. 

![examplepoam](https://user-images.githubusercontent.com/93686063/223236035-03d60435-928f-4f37-a817-84be5e6d9331.JPG)

The ISSM is responsible to create the POA&M as part of the SSP. The evaluation process is done by the ISSP/SCA and they determine the next steps. THe monitoring is still taking place by the ISSM. 

The Information Security Officer(ISO) or Project Manager/System Manager(PM/SM) does the following tasks: 
  - Noncompliant security controls
  - controls that are not applicable 
  - remediations tasks
  - required resources
  - milestones and compeltion dates
  - inherited vulnerabilities

They initiate corrective actions. 

According to the RMF Process, the Authorizing Official (AO) approves or rejects the elements of the POA&M. 




