# OWASP-Top-10-2021-vulnerabilites

## About

    Open Web Application Security Project (OWASP) Top 10 is a standard awareness document containing the most common security risks. The project aims to implement the web security knowledge and help organizations in developing a secure website/assessing OWASP TOP 10 2021 vulnerabilities/ mitigating the vulnerabilities related risks.
    
------------------------------------------------------------------------------------------------------------

## What this project Does
    
    It implements/mitigate the vulnerabilites related to OWASP TOP 10 2021 by installing pen-testing lab enviroment in virtualized environment that have the following virtual machines(VM). 
    - VM1: A web server-hosted website with OWASP TOP 10 2021 vulnerabilities.
    - VM2: The KALI Linux machine.
    - VM3: Opnsense web application firewall (WAF) running to inspect traffic destined for virtual machine 1 and patch the OWASP TOP 10 2021 vulnerabilities. To know more about <a href="https://opnsense.org/"> Opnsense.</a>
   ![image](https://user-images.githubusercontent.com/122940334/216792465-77977b05-b0ca-44d8-bc7e-385757c5a4b4.png)
 
----------------------------------------------------------------------------------------------
## How This Project Is Done

   First, Web Application Firewall (WAF) has been set up and configured by installed Opnsense WAF iso image and used it to create the WAF as a virtual machine within VirtualBox. Also, bWAPP vulnerable web app has been installed inside the other VM. 

