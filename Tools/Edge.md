We will now be Stigging the Microsoft Edge Browser. First we will be going to the DOD Cyber Exchange and get the files we will need in order to run the SCAP compliance checker and the STIG viewer.

![ed](https://user-images.githubusercontent.com/93686063/231459014-b3abd32b-a176-4b3e-a0d4-e68af2a40b2b.JPG)

We will install the Benchmark and then check the right profile and make sure only MS edge is checked in the Content tool and Start the Scan.

![ed1](https://user-images.githubusercontent.com/93686063/231459995-1de2b4d2-2cbc-44d5-ace9-4dc7f48f256a.JPG)

![ed2](https://user-images.githubusercontent.com/93686063/231460305-7b4c34a1-d1bb-4b8b-9c26-3bae85287b08.JPG)

The results of the Scan came out and we are 100% compliant. We can move on from this and stig other systems but we can also check for anything in the Stig viewer. The process will be the same. We will first install the checklist for Edge that we downloaded earlier from the document library and then we will save that checklist. 

![ed3](https://user-images.githubusercontent.com/93686063/231460943-295d195b-a9f8-409d-a696-733549f08448.JPG)

We will now import the `XCCDF` file and see what can be done in order to be fully compliant. Since the browser had all the security controls in place, we do not need to do anything about it. We can see the following result when we put our results in the stig viewer in comparison to the benchmark that we got from the document library. 

The Result is as follows: 

![ed4](https://user-images.githubusercontent.com/93686063/231461781-112716b4-9a3b-4ca7-82f6-57108a8058b6.JPG)
