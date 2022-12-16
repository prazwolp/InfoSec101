Beef is short for the Browser Exploitation Framework. It is a penetration testing tool that focuses on the web browser. Beef allows the professional penetration tester to assess the actual security posture of a target environment by using client-side attack vectors. Unlike other security frameworks, Beef looks past the hardened network perimeter and client system, and examines exploitability within the context of the open door: the web browser. Beef will hook one or more web browsers and use them as beachheads for launching directed command modules and further attacks against the system from within the browser context. 

The Beef project uses Github to track issues ad host its git repository. A read only copy of the repository can be found in `git clone https:github.com/beefproject/beef`. 

In order to install it, we go to the terminal and type in `apt-get install beef-xss`. After the installation is complete, when we look for Applications, we will see  `Beef Start` & `Beef Stop`. Our login will be userename `Beef` and password `kali`. 

`* Just in case you forget your password, open the file usr/share/beef-xss/config.yaml and look for the username and password` 
![beef](https://user-images.githubusercontent.com/93686063/208189542-df6105e3-b339-4cda-8442-a8312973eae0.JPG)

