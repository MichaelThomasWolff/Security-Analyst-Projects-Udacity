#Project 2: Insecure Juice Shop

**Section 1: Threat Assessment**
It’s time to get to work! You’ve arrived at one Udajuicer’s headquarters located in Miami and are shocked at the lack of technology. You ponder how in the world is this the largest juice shop without ever using computers or relying on technology. After the initial shock, you’re ready to get back on track and get to work. Manu, the eccentric owner, takes it upon himself to work with you directly to make sure you have everything you need. You first request an architecture diagram of the application and logs from right before the application went down. At a quick glance you notice the woefully designed architecture and buckle up for a long day, all the whilst Manu is in your ear talking about Super Smoothies evil plot to take down his franchise.

An architecture diagram showing a very sparse setup with only one web server, one application server, one database, and no security.
Manu's "Woefully Designed" Architecture

**Task 1: Asset Inventory**
The first part of our threat model is being able to identify all the assets involved in the target of the assessment. What does Udajuicer have of value? Looking at the architecture diagram, identify all the components that make up Udajuicer and document them in the assessment scope of your report. After identifying all the parts, explain the function of each part and how a request goes from the client to the server.

**Task 2: Architecture Audit**
Now that we’ve identified all the components that makeup Udajuicer, let’s conduct an architecture review with the given diagram. Referencing what we went over secure architecture best practices, list out at least 3 flaws.

**Task 3: Threat Model**
Build a Threat Model Diagram showing the flow of data using OWASP Threat Dragon. Identify at least 3 possible threats that would pose a threat to your web application. Think of the OWASP Top 10.

**Task 4: Threat Analysis**
We’ve now identified a few insecurities in Udajuicer’s architecture and want to use this knowledge to help us identify what was causing Udajuicer's website to crash. When in doubt, investigating logs should point us in the right direction. Analyze the log file on the desktop to identify what type of attack took down the Juice Shop.

**Task 5: Threat Actor Analysis**
The final part of our assessment consists of us trying to identify who would possibly want to take down the Juice Shop? Below are possible threat actors that we’ve covered in our course. Select who you think would most likely be responsible for the attack and explain why.

Organized Crime
APT Groups
State-Sponsored Attack
Insider Threat
Hacktivist
Script Kiddie


