
We will first look into Workspaces in Kali Linux. Workspaces are used to separate the work you are doing. When you are trying to exploit a machine, you would want to enumerate the machine. Enumeration basically means gathering as much information that you can using passive scanning or OSINT. 

Inside msfconsole, when you type $`workspace`, it will tell you which workspace you are in. If you want to know how many workspaces you have and which one you are working in you use $`workspace -v`. 

If you need to create a new workspace then you type $`workspace -a test`. The asterisk symbol is pointing to the workspace that you are currently in. If you need to delete a workspace then $`workspace -d name`. If you want to change the workspace then you just type $`workspace name`

We do this in order to keep track of all the work that we are doing without getting things too confusing between them. If we need to learn more about workspace $`help workspace`






