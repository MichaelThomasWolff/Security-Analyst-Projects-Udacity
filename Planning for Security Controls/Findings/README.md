# Project 1: Planning for Security Controls - Findings
**Task 1: Use the NIST work book and assign a score to each of the controls and inform your decisions.**

[NIST Work Book Solution](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/NIST%20Work%20Book%20Solution.xlsx)

**Task 2: Based on your analysis provide physical and logical controls that can be implemented to enhance the security posture of the company.**


Physical Control Recommendations
We don’t have much information about the physical environment of “Company A”. While the company operates from an office park, sharing premises with several other companies, I believe it is good practice to install the following (in addition to key-card access system and electronic locks as a replacement for mechanical locks):

•	Workstation locks 
•	Security cameras
•	A lockable cabinet for the network components to prevent tampering
•	Receptionist who escorts visitors
Logical Control Recommendations
Logical controls are mechanisms that protect information assets with rules about how data is accessed, transmitted, processed, and stored within the context of a system or application. 
The following would be recommended:

•	To achieve a secure architecture, we would add a firewall before the DMZ, in addition to the firewall that is installed before the LAN.

•	Add an Intrusion Detection System (IDS) behind the firewall on the edge of the network. 

•	If the website appears to use unencrypted (http) communications, it should be configured to use https since it is being used to handle eCommerce. 

•	Web API security is concerned with the transfer of data through APIs that are connected to the internet. Transport Layer Security (TLS) encryption for Rest API and Web Services Security (WS Security) for SOAP APIs are standards that keep an internet connection private and check that the data sent between two systems (a server and a server, or a server and a client) is encrypted and unmodified.

•	Ideally, MySQL would be not available through the network and all connections would be handled locally, through the Unix socket. 
Another solution would be the use of a firewall to allow traffic only from specific hosts to the MySQL server. This will limit possibilities of attack on the database.


Administrative Control Recommendations
(include the names of the attached policy documents)

Company A - Password-Protection-Policy.docx

Company A - Pandemic-Response-Planning-Policy.docx



**Task 3: Customize SANS security policies for use by the company.**


**Task 4: Make an inventory of hard- and software recommended by OpenVPN.**


**Task 5: Make an inventory of potential integration points.**


**Task 6: Make a high-level checklist of necessary deployment steps.**


**Task 7: Include your findings by completing the deployment plan.**


**Task 8: Make an inventory of hard- and software recommended by Duo 2FA.**


**Task 19: Make a high-level checklist of necessary deployment steps.**


**Task 10: Include you findings in the deployment plan document.**


**Task 11: Update the network diagram with the appropriate components necessary to deploy the proposed security solution.**


