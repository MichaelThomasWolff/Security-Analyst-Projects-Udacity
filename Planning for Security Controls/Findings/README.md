# Project 1: Planning for Security Controls - Findings
**Task 1: Use the NIST work book and assign a score to each of the controls and inform your decisions.**

Scores assigned to: [NIST Work Book Solution.xlsx](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/NIST%20Work%20Book%20Solution.xlsx)

**Task 2: Based on your analysis provide physical and logical controls that can be implemented to enhance the security posture of the company.**


**Physical Control Recommendations:**

We don’t have much information about the physical environment of “Company A”. While the company operates from an office park, sharing premises with several other companies, I believe it is good practice to install the following (in addition to key-card access system and electronic locks as a replacement for mechanical locks):

* Workstation locks
* Security cameras
* A lockable cabinet for the network components to prevent tampering
* Receptionist who escorts visitors

**Logical Control Recommendations:**

Logical controls are mechanisms that protect information assets with rules about how data is accessed, transmitted, processed, and stored within the context of a system or application. The following would be recommended:

* To achieve a secure architecture, we would add a firewall before the DMZ, in addition to the firewall that is installed before the LAN.
* Add an Intrusion Detection System (IDS) behind the firewall on the edge of the network. 
* If the website appears to use unencrypted (http) communications, it should be configured to use https since it is being used to handle eCommerce. 
* Web API security is concerned with the transfer of data through APIs that are connected to the internet. Transport Layer Security (TLS) encryption for Rest API and Web Services Security (WS Security) for SOAP APIs are standards that keep an internet connection private and check that the data sent between two systems (a server and a server, or a server and a client) is encrypted and unmodified.
* Ideally, MySQL would be not available through the network and all connections would be handled locally, through the Unix socket. 
Another solution would be the use of a firewall to allow traffic only from specific hosts to the MySQL server. This will limit possibilities of attack on the database.


**Administrative Control Recommendations:**

(see Task 3)


**Task 3: Customize SANS security policies for use by the company.**

[Company A - Password-Protection-Policy.docx](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/Company%20A%20-%20Password-Protection-Policy.docx)

[Company A - Pandemic-Response-Planning-Policy.docx](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/Company%20A%20-%20Pandemic-Response-Planning-Policy.docx)

**Task 4: Make an inventory of hard- and software recommended by OpenVPN & Duo 2FA. Include your findings by completing the deployment plan.**


**OpenVPN Implementation**

**Overview**

What it is: VPN stands for Virtual Private Network which allows to create a network that exists purely in software to connect computers over real networks securely by encrypting all of the data that’s being transferred. 
A VPN allows you to create a secure virtual tunnel to our office network through the public network such as the internet. It protects confidentiality (data remains secret via encapsulation) and integrity (data remains unaltered via encryption) of data as it travels over the public internet. 

How it works: The user first connects to the internet and then initiates a VPN connection via a locally installed client software (or web browser) to the VPN server located in the office. The VPN server based on your access level permission grants you access to internal company resources via the secure tunnel; thus, keeping data secure and private over the internet.
In this example we will install Remote-access VPNs. As the name implies, Remote-access VPNs allow mobile employees or remote workers to access their company’s intranet from home or anywhere in the world using their personal computers or mobile phones. Users can access the resources on the office computers as if they were directly connected to the office network. 

What we need: We will need a VPN access server and VPN client software. 
The two most commonly used technologies in remote access VPNs are IPsec and SSL. In this example we will use OpenVPN (SSL). 
OpenVPN is a full-featured SSL VPN which implements OSI layer 2 or 3 secure network extension using the industry standard SSL/TLS protocol, supports flexible client authentication methods based on certificates, smart cards, and/or username/password credentials, and allows user or group-specific access control policies using firewall rules applied to the VPN virtual interface.


**Hardware & Software Requirements, Possible Integrations**

OpenVPN Access Server does not create or manage its own dedicated user database. Instead, it
integrates with a user authentication database system. The currently supported systems are Active Directory/LDAP Server which we have already installed on-premises. OpenVPN server supports multiple authentication protocols and thus can be configured to obtain connecting client information from an LDAP server, and to use that information as a basis for authenticating the client in addition to the use of the Client certificates and keys.

**Requirements**

Hardware:

VPN Access Server (Linux machine)

Software:

On Client side: 

OpenVPN Connect for Windows

OpenVPN Connect for Mac (design department)

On Server side:

OpenVPN Access Server source code

Pricing:

Access Server subscription / 200 users / year $4632 / month $484

**Deployment steps:**

* Set up physical server with OpenVPN Access Server software
* Add OpenVPN LDAP plugin to OpenVPN Access Server
* Configured OpenVPN Access Server to obtain connecting client information from company LDAP server
* Configure firewall 
* Install OpenVPN client software on workstations
* Please view OpenVPN Network Diagram WorkBook.jpg

**OpenVPN Access Server / LDAP / Active Directory:**

* In order to setup an office VPN to support working from home, we will need to purchase, install and configure a hardware device as OpenVPN Access Server in our office location.
* With LDAP, you can use an Active Directory domain controller or other LDAP server to validate user credentials. Define these settings for Access Server to properly look-up user credentials when attempting to authenticate. 
* To configure OpenVPN LDAP based authentication, you need to install OpenVPN plugin for LDAP authentication which implements username/password authentication via LDAP for OpenVPN.
* Note: Be aware that LDAP authentication is not case-sensitive (with the exception of a user’s password) but Access Server is.
* LDAP allows you to configure the Authentication protocol for LDAP. You must also have an LDAP server already prepared if you want Access Server to authenticate using the LDAP protocol.
* Once you have the necessary plugins in place, the next thing would be to configure OpenVPN server for LDAP based authentication.
* Access Server will only look-up the provided credentials and grant access if matching credentials are found in the LDAP server and if the conditions for access defined in Access Server are met.

**Additional Administrative Considerations**

Firewall: 

* A firewall is a tool used to maintain the security of a private network. Firewalls block unauthorized access to or from private networks — and are often used to prevent unauthorized web users or illicit software from gaining access to private networks connected to the internet.
* Disabling a firewall is putting the entire network at risk. Rather than turning off a firewall altogether, you can open the appropriate (non-standard) ports in the firewall to allow authorized applications or services through. Some firewalls use a pre-defined port or range of ports, while others allow users to manually configure which ports the software utilizes.
* Enterprise VPN, Access Server, provide Layer 3 virtual private networking using OpenVPN protocol. OpenVPN protocol uses SSL/TLS with client and server certificates to perform key exchange and mutual authentication.


**Duo 2FA Implementation**

**Overview**

What it is: Two-factor authentication adds a second layer of security to your online accounts. Verifying your identity using a second factor (like your phone or other mobile device) prevents anyone but you from logging in, even if they know your password.

How it works: With Duo2F the user may log in as usual with his/her username and password, and will then receive a push message on the user’s device where he/she can verify that it is him/her. The administrator can set up the system to work via SMS, voice call, one-time passcode, the Duo Mobile smartphone app etc.
If you have a hardware token, you can press its button to generate a passcode. You can also use a Security Key (including U2F tokens).


**Hardware & Software Requirements, Possible Integrations**

Hardware:

* Hardware token or security key 

Software:

* Duo2F for mobile
* Duo OpenVPN v2.4 plugin
* Duo2F Wordpress plugin

**Duo 2 Factor Authentication setup:**

* Enrollment and setup accounts
* Install Duo mobile apps
* Activate Duo Mobile
* Install and setup Duo2F for OpenVPN (Ensure that Python 3 or 2.7 is installed on server)
* Install and setup Wordpress plugin
* Please view Duo2F Network Diagram WorkBook.jpg

**Additional Administrative Considerations**

Duo only integrates with OpenVPN servers that employ certificate authentication and use a unique common name (CN) in each user's cert. Support for OpenVPN deployments with password authentication may be supported in the future.


**Task 11: Update the network diagram with the appropriate components necessary to deploy the proposed security solution.**

![alt text](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/OpenVPN%20Network%20Diagram%20Solution.jpg)

![alt text](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/Duo2F%20Network%20Diagram%20Solution.jpg)

