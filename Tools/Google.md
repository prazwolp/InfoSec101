The process of Stigging is not only performed on Operating systems but they are also highly used for applications that we use on a daily basis such as Google Chrome browser, firefox, edge, etc. For this tutorial we will be stigging the Google Chrome browser. The first step in the process is to download the benchmarks for the browsers from the STIG Document Library. 

![gc](https://user-images.githubusercontent.com/93686063/231455613-84a68f4a-dde0-49ea-a071-04a5939353e5.JPG)

Once we have the documents, we will extract those documents and start the Scap Compliance Checker. We will install the Benchmark for the Google Chrome Current Windows version and Install it and check it just so that we will be running our SCAP Compliance checker on the checked application and not on other contents that we have on our content bar. We will check the profile depending on whichever environment that we are working on, such as Public, Sensitive and Classified.

![gc1](https://user-images.githubusercontent.com/93686063/231456436-2ec95955-5ade-44ed-b3dc-39b836725e65.JPG)

Once our scan is complete we will go out and look for any vulnerabilities that we can find, we will specially be on the look out for the CAT 1 vulnerabilities as they are the most serious ones that will needed to be taken care of immediately in order to protect the systems. 

![gc2](https://user-images.githubusercontent.com/93686063/231456974-b9807380-ad9c-4bda-bf48-160a48936ef3.JPG)

Our browser is fully compliant so we do not really need to check for anything else but we can still put the results `XCCDF` file on our STIG viewer to have a detail analysis of the browser and its compliance. We get the following result. 

![gc3](https://user-images.githubusercontent.com/93686063/231457648-a8ddf8c9-dda9-44ce-8afd-96e8b3cbb2ea.JPG)
