Splunk is a software solution that falls under the category of Security Information and Event Management (SIEM). When you configure Splunk in your enterprise, you configure it to ingest data from a wide variety of sources, which then allows you to search through it. You can also create visualizations such as dashboards. Splunk has a number of server components that run on different platforms. You can also work with Splunk as a managed cloud service. Splunk also allows you to automate alert notifications. 

SIEM solution is like a large funnel into which all IT services report their usage infromation and performance metrics to. SIEM capabilities include centralized security monitoring and data analytics and data corelation. SIEM enterprise solution collect data from a variety of different sources, so it gets funneled into a centralized location where data analysis and correlation takes place. So, for example through machine learning if there is suspicious behavior, an alert will be generated. Data analysis and correlation can be used for threat detection. Threat detection is something that can change over time, for instance if it was normal to have only Windows hosts and now all of a sudden the organization has started seeing Linux hosts then it can generate an alert. Now the organization could have just added a new workstation so we can stop having alerts for those events.

We also have the Security Orchestration, Automation and Response (SOAR) component. SOAR has more to do with incident response which if ideal will be automated. They can be 100% automated but it could work as a hybrid feature where some of the responses have to be done manually in order to respond to an event. Splunk has more than 300 3rd party tools that can integrate with playbooks to help automate incident response actions. SOAR is often used as a way to ingest large amounts of data through SIEM and then stop that malicious activity to actively do something about it. Things that should be considered for automating for detection and containment of potential security issues would be malware incident things like Ransomware outbreaks and crypto minings which can use up precious CPU processing power on servers. 

`Splunk Components:`
  - Splunk Enterprise runs on multiple platforms like Windows, Linux, macOS
  - Splunk Cloud platform 
  - Splunk Enterprise console (listens on port 8000)
  - Splunk Cloud Console (comes with DNS fully qualified domain name) 

`Splunk Forwarders:`
  - Splunk Forwarder is a software agent that gets deployed on a host. With a forwarder we can determine what data it will collect by a file called `inputs.conf`. You can         determine where that data will go, such as being forwarded to an index or elsewhere in the `outputs.conf` file. There are two main types of forwarders, universal and           heavy. 
  - `Universal Forwarder` deals with raw unfiltered data whereas the `Heavy forwarder` is designed so that it will filter data at the source before sending it off to an            indexer.
  
  Universal forwarder can do a bit of filtering, it can perform basic filtering events like filtering windows events by IDs, but if you want more complex regular expression     pattern matching, one would have to use a universal forwarder. 
  `Splunk Indexer` does data parsing. It processes input data streams from forwarders With `Data Indexing` parsed items get written do disk index and can be searched. 
  The file `transforms.conf` can determine which events are sent to which indexes. 
  `Splunk Search head` is a component which in a web console that listens by default on port 8000. There are many Splunk based apps. It is a packaged up way to apply         something to your Splunk environment. 
  
  `Deployment Server` is optional and is used mostly on a large environment. A lot of forwarders because the deployment server is designed as a centralized way to manage      the configuration of multiple forwarders. 
  
  `Splunk Data Ingestion` 
  A crucial part of Splunk is configuring data ingestion. We need to be able to receive data into our Splunk environment so it can be indexed and then it can be searched,      we can generate reports, we can generate dashboard visualizations and so on. We have a lot of Splunk data sources such as operating system logs, which could be             application-specific or cloud-based logs for your cloud environment, i.e. Amazon web services, GCP, Azure and so on. One can also use AD as a data source. 
  
  
