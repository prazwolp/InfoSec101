There are two kinds of deployment that we can do and they are either `Splunk Enterprise` or `Splunk Cloud` 

`Splunk Enterprise` 
  - Splunk enterprise can be a manual installation of the Splunk enterprise software that one can download on physical or virtual machines, whether they are on premises or in     the cloud. In case of AWS, you can quickly deploy Splunk Enterprise by using an AMI. An AMI deployment means you basically choose a Splunk enterprise OS image and quickly     deploy the virtual machine, but you can still get full configuration flexibility like a manual installation. It also gives you command line or CLI Support. 
 
 `Splunk Cloud` 
  - If we were to deploy Splunk Cloud, we do not need to worry about the underlying infrastructure, the network setup, the virtual machines. However with the Cloud there are       limited configuration flexibility compared to enterprise, such as at the operating system level and the Splunk Cloud Platform does not support a CLI. 
 
 All your forwarders can relay data to either the Enterprise or the Cloud. The Splunk Deployment Server (DS) is optional. It is used to manage groups as forwarders. 
 
![DS](https://user-images.githubusercontent.com/93686063/228652646-d9042f33-a0b8-48bf-be6f-f8f134dee785.JPG)

Authentication can be used in your deployments, which is to say users and roles will be treated. You can create Splunk user accounts directly in Splunk and one can assign them roles. You might also create custom roles based on your needs because a role is how users get permissions. One might have a role, for example, that allows access to search through a particular index and only that index. You could also have external Splunk authentication. For example, link through an LDAP configuration, your Splunk environment to an Active Directory environment. One can configure a password policy on Splunk, enable single sign-on, and also multi-factor authentication for enhanced security. 

`Splunk Enterprise Deployment in Linux` 



