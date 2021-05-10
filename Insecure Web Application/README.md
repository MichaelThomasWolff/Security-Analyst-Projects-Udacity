# Project 3: Insecure Web Application

## Section 1: Assessment

The first request is an architecture diagram of the application and logs from right before the application went down. At a quick glance you we notice that the architecture is designed woefully. 
Task list:
**1. Asset Inventory**
The first part of our threat model is being able to identify all the assets involved in the target of the assessment.
**2. Architecture Audit
Now that we’ve identified all the components that makeup Udajuicer, let’s conduct an architecture review with the given diagram. Referencing what we went over secure architecture best practices, list out at least 3 flaws.
**3. Threat Model**
Build a Threat Model Diagram showing the flow of data using OWASP Threat Dragon. 
**4. Threat Analysis**
We’ve now identified a few insecurities in Udajuicer’s architecture and want to use this knowledge to help us identify what was causing the website to crash. Analyze the log file on the desktop to identify what type of attack took down the Juice Shop.
**5. Threat Actor Analysis**
The final part of our assessment consists of us trying to identify who are possible threat actors.

## Section 2: Vulnerability Analysis
You’ve made it past the initial assessment and still have your sanity as working with Manu can be exhausting. You’ve identified the initial attack and shortcomings of the application setup. 
**1. SQL Injection**
The first vulnerability we want to exploit is on the login page of the website. The login portal is subjectable to a SQL Injection attack.
**2. XSS**
The second vulnerability we want to exploit is after we’ve logged into the site. We want to exploit an XSS vulnerability in the search bar. 


## Section 3: Risk Analysis
After notifying the owner of two more vulnerabilities, he next step is to rank the risks in order of what should be dealt with first.

**1. Scoring Risks**
Use the matrix in the Threat Model Report to score the risks that we’ve identified so far to the Juice Shop.
**2. Risk Rationale**
Now that we’ve scored all our risks, explain why you chose to rank the risks in the way you did. 



