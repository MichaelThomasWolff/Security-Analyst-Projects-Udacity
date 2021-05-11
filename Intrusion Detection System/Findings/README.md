# Project 4: Intrusion Detection System - Findings

## Incident Ticket

Detection (network events, host events, external report):

## Initial detection/IoC:

2020-Jun-06 22:00:50	216.154.220.53:80	 --> 10.0.0.12:50134


## Additional indicators (incl. network traffic, host logs):

The following entries were detected 

10.0.0.12 --> 190.6.193.152           POST /w00n19tnKeyeyjNO HTTP/1.1

Content-Type: application/x-www-form-urelencoded

190.6.193.152 --> 10.0.0.12           HTTP/1.1 (text/html)


10.0.0.12 --> 216.154.220:53	HTTP	433	GET /malware/fnpufu.exe HTTP/1.1 

216.154.220:53 is identified as a server in the USA.

The detected file fnpufu.exe was extracted and the SHA-256 hash: 006d5fda899149df4cc5d6d1b1ae52e9fcc4ade7541c1dd4391e0429d843b4d5, was checked against VirusTotal, which defines the malware as Trojan Emotet AFS.


## False Positives

(Note: in the real world, false positives are not logged in an incident ticket. This section is unique to our project)

2020-Jun-06 21:59:17	172.31.90.209:35997 --> 172.31.0.2:53

2020-Jun-06 21:57:09	192.168.1.56:36982	 --> 34.239.152.87:80

2020-Jun-06 21:57:20	192.168.1.56:36984 --> 34.239.152.87:80

2020-Jun-06 21:57:33	192.168.1.56:36986 --> 34.239.152.87:80

2020-Jun-06 21:57:52	192.168.1.56:36988	 --> 34.239.152.87:80

2020-Jun-06 21:58:05	192.168.1.56:36990 --> 34.239.152.87:80

2020-Jun-06 21:58:20	192.168.1.56:36992	 --> 34.239.152.87:80

## Containment:

* We are identifying the infected assets(s) and physically disconnect them from the network:
* 22:10 The Network Operations Center (616-555-4662) has been contacted and the on-call staff has been asked to disable network access to the wall jack (desktop) or network switch (data center).
* Copies of the malicious code, affected systems and any identified artefacts
for further investigation are secured.
* Business continuity options for users affected by such disconnection include:
a) Replacing disconnected devices with fresh builds from IT, where stocks
permit (ensuring they first have relevant updates applied). 
b) Directing users whose devices are disconnected to work from an alternative
location; such as another office, a Disaster Recovery facility or from home.
* The account passwords for any system users will be reset, including local and administrative accounts. Help Desk (616-555-4357) will assist with this.
* Login credentials of suspected compromised accounts are suspended

## Analysis (other compromised hosts, lateral movement, data exfiltration, etc.):

* We are monitoring for any new infections which might suggest that the malware is spreading across the infrastructure.
* The latest malware definitions have been deployed across the antimalware solution.
* An estate-wide anti-malware scan is initiated. 
* We will determine whether the malware appeared to be communicating with
outside parties and take steps to block any such communication.
* We will Inform business data owner(s) and stakeholders of the progress of containment activities.


## Recovery:

* Complete malware scanning of all systems, across the estate.
* Re-image systems.
* Re-set the credentials of all involved system(s) and users account details.
* Restore any corrupted or destroyed data.
* Restore any suspended services
Post-incident recommendations:
Draft a post-incident report that includes the following details as a minimum:
* Details of the cyber incident identified and remediated across the network to
include timings, type and location of incident as well as the effect on users;
* Activities that were undertaken by relevant resolver groups, service providers
and business stakeholders that enabled normal business operations to be
resumed;
* Recommendations where any aspects of people, process or technology could
be improved across the organization to help prevent a similar cyber incident
from reoccurring, as part of a formalized lessons identified process.
* Complete the formal lessons identified process to feedback into future preparation
activities.
* Consider sharing lessons identified with the wider stakeholders.
* Conduct root cause analysis to identify and remediate underlying vulnerabilities.
* Publish internal communications in line with the communications strategy to inform
and educate employees on malware attacks and security awareness

![alt text](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/OpenVPN%20Network%20Diagram%20Solution.jpg)

![alt text](https://github.com/MichaelThomasWolff/Security-Analyst-Projects-Udacity/blob/main/Planning%20for%20Security%20Controls/Findings/OpenVPN%20Network%20Diagram%20Solution.jpg)

