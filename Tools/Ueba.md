`User Entity Behavior Analytics (UEBA)` 

UEBA is a cybersecurity solution that uses algorithms and machine learning to detect anamolies in the behavior of not only the users in a corporate network but also the routers, servers and endpoints in that network. 

UEBA seeks to recognize any peculiar or suspicious behavior instances where there are irregularities from normal everyday patterns or usage. For example, if a particular user on a network regularly downloads files of 50 MB every day but starts downloading 5GB of files the UEBA system would consider this an anamoly and either alert an IT administrator, or if automations are in pace, automatically disconnect the user from the network. 

UEBA not only monitors human behavior but also monitors machines. A server in one branch office may suddenly received thousands more requests than usual one day, signalling the start of a potential distributed denial of service attacks, there is a chnace IT administrators might not notice this type of activity, but UEBA would recognize it and take further action. 

For a UEBA solution to be effective, it must be installed on every device used by or connected to every employee across the organization. This includes devices not only owned by the company but also owned by the employee, as even devices used part time can be targets of a cyberattack. Some organizations may also request that employees install the UEBA solution on their home routers. 

After installation the UEBA goes silent as it starts collecting data on device and network usage. In `learning mode`, the UEBA solutions algorithms will determine and further define what is considered normal or even optimal. IT admins decide how long the learning mode will last before the system goes into testing mode. 

The three main componenets of a UEBA Solution are as follows: 

   `Analytics ->`
                collects and organizaes data on what is determined to be normal behavior of users and entities. The system builds profiles of how each normally acts                         regarding application usage, communication and download actiivity, and network activity. Statistical models are then formulated and applied to detect                       unusual behavior.
                
   `Integration ->`
                 Intergrate with other security products and systems already in place is a must as organizations grow and evolve. They most likely have a security stake in                  place, which may include legacy systems that may not keep up with today's ever-increasing threat landscape. The beauty of UEBA is that it is not meant to                    obviate existing security products in use across the enterprise. With proper integration, UEBA systems are able to compare data collected from various                      sources, including logs, packet capture data, and other datasets, and integrate these to make the sytem more robust.  
                 
   `Presentation ->`
                 It is the process of communicating the findings of the UEBA system and devising an appropriate response. This can vary between organizations, some UEBA                      systems will simply create an alert, either for the employee or the IT administrator, to suggest further investigation. Other UEBA systems will be set up                    to take immediate action - by automatically shutting off network connectivity for the at employee due to a suspected cyberattack, for example. 
 
 
 Some of the types of insider threats includes: 
   - Privileged account abuse: (Inappropriate use of access permissions) 
   - Privilege escalation: (Change of access credentials)
   - Data Exfiltration: (Theft of private, confidentail and sensitive data within an organization by malware or an infiltrator)
   - Anamalous behavior: (Accessing external domains, remotely accessing high-privileged assets and unsual login duration, time or location) 
   - Credential compromise: (Stealthy takeover of accounts for malicious purposes)
 
 Splunk uses these tools in order to get the date for monitoring. 
 
 ![ueba](https://user-images.githubusercontent.com/93686063/228330151-46a78e8f-6669-4b11-b7ab-662517b6df0f.JPG)
 
 
What is the difference between UBA and UEBA?

User behavior analytics and user and entity behavior analytics are essentially synonymous. Most UBA solutions also cover the “entity” aspect that led Gartner to coin “UEBA.” However, UEBA is arguably the more common term because it makes the key distinction between user and entity behavior. (“UBA” is also the name of the Splunk UEBA tool that helps organizations fight insider threats through multidimensional behavior baselines, dynamic peer group analysis and unsupervised machine learning.)
How does UBA/UEBA work?

UBA/UEBA works by looking at the deviations in a user or asset’s behavior when compared to past actions or peer groups. A UBA solution will create a baseline for each user, device, application, privileged account and shared service account, then detect standard deviations from the norm. It will subsequently assign a score to indicate the intensity of the threat in question, letting the enterprise not only review alerts on a daily basis, but also watch top malicious users and take preventive action.
How do you resolve threats with UBA/UEBA?

Rather than providing a torrent of alerts triggered by static rule violations, UBA delivers a shorter list of threats to resolve, along with supporting evidence to explain why a specific threat should be of concern.

Security analysts have a number of options for resolving threats discovered by UBA. In addition to viewing threats through the user interface, threat information can be emailed to remediation staff such as IT/security help desks; published to a security dashboard; or forwarded to an external ticketing or security system. Depending on where your UBA solution plugs in, you might also have an automated response that fires off when an incident or event is detected.

 ![ueba1](https://user-images.githubusercontent.com/93686063/228330707-d6275b25-0928-43e1-ac7e-9e539bb23a98.JPG)


How do you use UBA with SIEM?

UBA is a vital component of any SIEM (security incident and event management) system. UBA tools work in concert with SIEM solutions to provide insight into behavioral patterns within the network. By combining both solutions, you reap the benefits of threat detection techniques that examine both human and machine behavior.

 

Explore Splunk SIEM for Enterprise Security.

Expanding your SIEM to ingest behavioral anomalies detected by UBA also provides additional context around known and unknown threats, as well as identifies the threats more accurately. This can save analysts’ time and increase your SOC efficiency by eliminating false positives and only surfacing high-fidelity threats that can’t typically be detected through rules-driven correlation.
What is UBA’s role in a security operations center (SOC)?

UBA plays a critical role in the security operations center, identifying unusual changes in end-user behavior. UBA can filter alerts before they’re raised to the SOC team, giving them time to focus on urgent and complex threats.

UBA allows SOC analysts to seamlessly and easily:

    Identify insider threats with behavior modeling and peer group analytics.
    Focus on insider threat detection through anomaly scoring.
    Automate incident response and monitor threats continuously.

Adaptive information security architectures that incorporate this type of advanced analytics are better able to prevent, detect and respond to cyber attackers in today’s security landscape.



