Beef is short for the Browser Exploitation Framework. It is a penetration testing tool that focuses on the web browser. Beef allows the professional penetration tester to assess the actual security posture of a target environment by using client-side attack vectors. Unlike other security frameworks, Beef looks past the hardened network perimeter and client system, and examines exploitability within the context of the open door: the web browser. Beef will hook one or more web browsers and use them as beachheads for launching directed command modules and further attacks against the system from within the browser context. 

The Beef project uses Github to track issues ad host its git repository. A read only copy of the repository can be found in `git clone https:github.com/beefproject/beef`. 

In order to install it, we go to the terminal and type in `apt-get install beef-xss`. After the installation is complete, when we look for Applications, we will see  `Beef Start` & `Beef Stop`. Our login will be userename `Beef` and password `kali`. 

`* Just in case you forget your password, open the file usr/share/beef-xss/config.yaml and look for the username and password` 



![beef](https://user-images.githubusercontent.com/93686063/208189542-df6105e3-b339-4cda-8442-a8312973eae0.JPG)

First we will type in `10.0.2.10` which is the web server `owasp` and go to `XSS Stored`. When we go there, we just use any name and on the message board, we hit `Right click and Inspect element`, for `maxlength` we will do `100` instead of `50`. Once we do this, we go back to the Kali terminal and find the `hook` which we will use to connect to the OS that will be connecting to us. Below is a picture of the hook that we will use. 

![hook](https://user-images.githubusercontent.com/93686063/208196633-2fb52de8-f5ce-4d06-a2de-08e5cce17751.JPG)

We can see that, our Linux is hooked, now we will try to hook the Windows Server 08. Once, the website is opened on the Internet Explorer we can see that Windows server is hooked. Now that we have them all connected. Once it is hooked, we can see the details. For this example we will use `Social Engineering -> Pretty Theft`

![beef2](https://user-images.githubusercontent.com/93686063/208197202-9e6311e6-3004-46ee-92b7-3ed3c047e68d.JPG)

If we hit execute, we will see a prompt on the Windows server 08 like below 

![prompt](https://user-images.githubusercontent.com/93686063/208197473-03492986-2c27-40d1-bacb-7b55664ad529.JPG)

A user who does not know much will put their information in there and it will be captured by the Beef and will be displayed as follows: 

![prompt2](https://user-images.githubusercontent.com/93686063/208197616-3510436e-cf48-4824-b244-809a2ccdcd14.JPG)


You will see the username and password used by the victim in Beef. 









