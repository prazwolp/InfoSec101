Now that we have the report, we can see the report and figure what can be remediated. 

![findings](https://user-images.githubusercontent.com/93686063/223222783-f195e3cc-7f73-45e9-ac12-84c5e0ac6da1.JPG)

On the report we can see that there are `94 open findings`. 163 findings that were closed or not vulnerabilities and 46 that were `not reviewed`. These `Not Reviewed` are likely manual checks, they cant be assessed automatically and must be reviewed manually. However not all of them will be vulnerabilities. The STIG viewer assists us in sorting through them and identifying any that need remediation. 

There are also some `CAT` tabs beside the Overall Totals that categorize the vulnerabilities that you might have. These are different levels of Security, Level 1 is the most severe and Level 3 is the least severe. The NISP does not require corrective actions for each of these levels, but best industry practices recommend we mitigate CAT 1 findings first. We should pay special attention to the `CAT 1` list. 

![Cat1](https://user-images.githubusercontent.com/93686063/223225705-006c655e-f0af-4f2c-a7b6-f2ece496c7f2.JPG)

Besides seeing the results in the pie chart, we can also see some color coding. a `Red O` indicates Open, a `green NF` is not a finding, and a `black NR` is not reviewed. So, for example if we were to look at Open finding `O V-3347` we can see that `Internet Information Services` enabled. In this case it means that someone from outside the network may be able to access information that they should not. 


`Check Content` 

![checkcont](https://user-images.githubusercontent.com/93686063/223226706-a23e31c4-c8fb-44f5-9b79-181bc6cb73f0.JPG)

`Fix Text` This is probaby the most important tab which will tell us how to remedy the problem. 


![fixtest](https://user-images.githubusercontent.com/93686063/223227008-e7763f9e-d709-420b-9c36-6840d04a59fe.JPG)


`CCI Tab` 

The CCI Tab helps us identify the Control Correlation Identifiers in the NIST SP 800-53. 

![cci](https://user-images.githubusercontent.com/93686063/223227315-51e14824-040e-4f8d-9f52-73de17403382.JPG)

Now we will look at some `Open Findings`. They could be false positive. The ISSM will make the final decision on taking corrective actions if required in order to keep the systems secure. 










