One of the ways that attackers get access to an environment is through password spraying, and also looking for exploited passwords online. A website that one can go to in check if there credentials has been compromised is $`haveibeenpwned.com` and those passwords can be reused. 

$`Password Spraying`

This is the following lab that we use in order to learn how to password spray. 

https://github.com/prazwolp/IntroLabs/blob/master/IntroClassFiles/Tools/IntroClass/PasswordSpray/PasswordSpray.md


The command `Invoke-LocalPasswordSpray -Password Winter2020` command will try the word `Winter2020` for all the users that are on the system. One should really be careful with password spraying attacks, since the account could be locked out for many unsuccesful attempts. So be careful with the password spraying during an offensive pentesting. 

