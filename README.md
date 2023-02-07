# OWASP-Top-10-2021-vulnerabilites

## About

   Open Web Application Security Project (OWASP) Top 10 is a standard awareness document containing the most common security risks. The project aims to implement the web security knowledge and help organizations in developing a secure website/assessing OWASP TOP 10 2021 vulnerabilities/ mitigating the vulnerabilities related risks.
    
------------------------------

## What this project Does
    
   It implements/mitigate the vulnerabilites related to OWASP TOP 10 2021 by installing pen-testing lab enviroment in virtualized environment that have the following virtual machines(VM):
    - VM1: A web server-hosted website with OWASP TOP 10 2021 vulnerabilities.
    - VM2: The KALI Linux machine.
    - VM3: Opnsense Web application firewall (WAF) running to inspect traffic destined for virtual machine 1 and patch the OWASP TOP 10 2021 vulnerabilities.

    
   ![image](https://user-images.githubusercontent.com/122940334/216792465-77977b05-b0ca-44d8-bc7e-385757c5a4b4.png)
   
 
-----------------------------------------------

## How This Project Is Done

   First, the Web Application Firewall (WAF) has been set up and configured by installing Opnsense WAF iso image and using it to create the WAF as a virtual machine within VirtualBox and bWAPP vulnerable web app has been installed inside the other VM. The bWAPP is a free and open-source web application that is intentionally designed to be insecure in order to assist security professionals, developers, and students in identifying and preventing web vulnerabilities. It provides a platform for conducting successful penetration testing and ethical hacking projects and is distinguished by its comprehensive range of over 100 web vulnerabilities, including those listed in the OWASP Top 10 project. Its purpose is to educate users on how to protect against web vulnerabilities and improve their skills in security testing. By installing the needed tools we successfully implemented the OWASP TOP 10 vulnerabilities and mitigated them.

-------------
## What I Learned

During this project, I and my teammates managed to expand our theoretical and practical knowledge regarding the OWASP top 10 vulnerabilities and web application security in general and described each category, and discovered a vulnerability for each category. After that, we managed to exploit and then mitigate each vulnerability either by using the web application firewall or by a modification in the source code. 

------------------------------------------------------------------------------------------------------------

## Demo For One Of the Project vulnerabilities

### Broken Access control

- Vulnerability description

    Access control vulnerabilities are weaknesses in the systems and processes that control who has access to resources or can perform certain actions. These vulnerabilities can allow unauthorized people to gain access to sensitive information or do things they should not be able to, which can lead to data breaches, identity theft, and other security incidents.The Open Web Application Security Project (OWASP) identifies broken access control as the most common issue found in web applications and lists it as the first category in the OWASP Top 10 2021. 
It is essential for organizations to implement robust access controls in order to safeguard against attacks and unauthorized access to sensitive resources. This can help prevent data breaches and other security issues, which can have serious impacts on the organization.The attack performed is associated with CWE-22: Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal'), CWE-23: Relative Path Traversal and CWE-36: Absolute Path Traversal.

- Hands on  
   
   From the attacker machine, we will open bWAPP website and select Directory Traversal – file bug from bug lest and go to “hack” button. 
   
   ![image](https://user-images.githubusercontent.com/122940334/216853220-88d3cbe7-805d-47ae-af65-51adf7ed87d4.png)
   
   On the Directory Traversal page that is shown to us, we see parameter lead to the file message.txt. we will enter the following string into the "page" parameter:  "../../../../../etc/passwd" . we know that in Linux , “..” go back to previous location. Here we are moving two level back and ask the passwd file from /etc directory in the root directory., instead of just reading message.txt file.
   
   ![image](https://user-images.githubusercontent.com/122940334/216853262-fdb3bc9d-1c13-4707-a1a7-6be40aea7983.png)
   
   If the attack is successful, the contents of the /etc/passwd file on the server will be displayed. This file contains a list of all the users on the system, along with their user IDs and other information. By accessing this file, an attacker can potentially gain sensitive information about the system and its users.
   
   ![image](https://user-images.githubusercontent.com/122940334/216853281-bb361288-cb3e-44e4-aa26-d4e67f205083.png)
   
- Mitigation 

  In OPNsense, a firewall rule can be configured to block directory traversal attacks. We have set the WAF rules to block multiple attacks, one of them is Directory traversal. We have configured the WAF back to learning mode to view the results of a successful attack.
  
    ![image](https://user-images.githubusercontent.com/122940334/216853362-8b17354c-a72f-4710-90f9-ec7fbb93db1a.png)
    
    Now any attempt to exploit the directory traversal and view passwd file or any other confidential file will be blocked. We can notice the malicious parameter in
    the URL field, and the error message shown to block the user from applying the attack.
    
    ![image](https://user-images.githubusercontent.com/122940334/216853399-140a1e51-5fcf-4c31-957d-e642206138a4.png)
    

----------------------

Please hit me up at <a href="https://www.linkedin.com/in/ghaidalamri"> Linkedin</a> if you have any questions or want more details.

    






   

