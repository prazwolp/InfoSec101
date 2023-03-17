`Cyber Threat Intelligence` 

Cyber Threat Intelligence(CTI) is vital for investigating and reporting against adversary attacks with organizational stakeholders and external communities. 
There are different modules that we will be covering in Cyber Threat Intelligence Module and they are as follows: 

  - Threat Intelligence Tools 
  - YARA 
  - OpenCTI
  - MISP

CTI can be defined as evidence-based knowledge about adversaries, including their indicators, tactics, motivations, and actionable advice against them. These can be utiltised to protect critical assets and inform cybersecurity teams and management business decisions. 

  - Data -> Discrete indicators associated with an adversary such as IP addresses, URLs or hashes. 
  - Information -> A combination of multiple data points that answere questions such as "How many times has an employee accessed certain website within a month?" 
  - Intelligence -> The correlation of data and information to extract patterns of actions based on contextual analysis. 

` The primary goal of CTI is to understand the relationship between your operational environment and your adversary and how to defend your operational environment against any attacks. You would seek this goal by developing your cyber threat context by trying to answer the following questions: ` 

  - Who's attacking you?
  - What are their motivations?
  - What are their capabilities?
  - What artefacts and Indicators of Comprimise(IOCs) should you look out for? 


When we try to answer these questions, we need to gather the information from different sources under the following categories: 

  - Internal -> Corporate security events such as vulnerability assessments and incident response reports, cyber awareness training reports and system logs and events. 
  - Community -> Open web forums and dark web communities for cybercriminals. 
  - External -> Threat intel feeds(Commercial and Open source), online marketplaces, public sources include gov data, publications, social media, financial and industrial                     assessments. 

`Threat Intelligence Classifications:` 
Threat Intel is geared towards understanding the relationship between your operational environment and your adversary, we can break down threat intel into the following classifications: 

  - Strategic Intel -> High Level intel that looks into the organizations threat landscape nad maps out the risk areas based on trends, patterns and emerging threats that                          may impact business decisions. 
  - Technical Intel -> Looks into evidence and artefacts of attack used by an adversary. Incident response teams can use this intel to create a baseline attack surface to                          analyse and develop defense mechanisms.
  - Tactical Intel -> Assesses adversaries tactics, techniques and procedures (TTPs). This intel can strengthen security controls and address vulnerabilities throuugh real-                       time investigations.  
  - Operations Intel -> Looks into an adversary's specific motives and intent to perform an attack. Security teams may use this intel to understand the critical assets                            available in the organization(people, processes and technologies) that may be targeted. 

![threat](https://user-images.githubusercontent.com/93686063/225945608-dc145974-ac06-400c-860c-576d10f4587f.JPG)


There are many websites which can help us to threat intelligence. Some of them are as follows: 

  - `urlscan.io` -> It is a free service developed to assist in scanning and analyzing websites. It is used to automate the process of browsing and crawing through websites                     to record activities and interactions. When a URL is submitted, the information recorded includes the domains and IP addresses contacted, resoures                           requested from the domains, a snapshot of the web page, technologies utilised and other meta data about the website. A urlscan example is as below. 

![url](https://user-images.githubusercontent.com/93686063/225992818-32777238-4a4d-4569-92cd-1d798509a309.JPG)

  - `Malware Bazaar` -> This project is an all in one malware colletion and analysis database. The project supports the features such as Malware samples upload and malware                          hunting. 
  
  - `FeodoTracker` -> (https://feodotracker.abuse.ch/) With this project, abuse.ch is targeting to share intelligence on botnet Command and Control(C&C) servers associated                       with Dridex, Emotes, TrickBot, QakBot and Bazaarloader/ Bazaar Backdoor. This is achieved by providing a database of C&C servers that security                               analysts can search through and investigate any suspicious IP addresses they have come across. Additionally, they provide various IP and IOC                                  blocklists and mitigation information to be used to prevent botnet infections.  An example is below. 


![feodo](https://user-images.githubusercontent.com/93686063/225994546-d36d87ad-e130-45d1-a7db-09575b63f94c.JPG)

  - `SSL Blacklist` -> (https://sslbl.abuse.ch/) Abuse.ch developed this tool to identify and detect malicious SSL connections. From these connections, SSL certificates by                         botnet C2 servers would be identified and updated on a denylist that is provided fro use. The denylist is also used to identify JA3 fingerprints                             that would help detect and block malware botnet C2 communications on the TCP layer.  Example below. 


![ssl](https://user-images.githubusercontent.com/93686063/225995235-f27f97c8-e57d-4c4d-bfb4-4a11b5a5a73d.JPG)

  - `URLhaus` -> (https://urlhaus.abuse.ch/browse/) This tool focuses on sharing malicious URLs used to malware distribution. You search through databases for domains,                     URLs, hashes and filetypes that are suspected to be malicious and validate your investigations. The tool also provides feeds associated with country, AS                      number, and Top Level doamins that an analyst can generate based on specific search needs. 

 ![url1](https://user-images.githubusercontent.com/93686063/225996261-514dbfda-986a-491f-bd14-ee1dc1ff906c.JPG)
 
  -  `ThreatFox` -> (https://threatfox.abuse.ch/) Security analysts ca search for, share and export indicators of compromise associated with malware. IOCs can be exported                        in various formats such as MISP events, Suricata IDS Ruleset, Domain host files, DNS Response Policy zone, JSON Files and CSV files. 

![threatfox](https://user-images.githubusercontent.com/93686063/225997612-45fe9131-6926-47e6-b778-23805ad949d4.JPG)


