# DEPLOYMENT-MIGRATION
### 1-BUSINESS REQUIREMENT

- DEPLOY AND HOST THE WEB APPLICATION ON AZURE TO IMPROVE PERFORMANCE AND REDUCE MAINTENANCE COSTS.
- MIGRATE DATABASES DB1 AND DB2 TO AZURE TO LEVERAGE THE CLOUD'S SCALABILITY AND RELIABILITY.
- MINIMIZE ADMINISTRATIVE EFFORT AND COSTS BY UTILIZING AZURE'S MANAGED SERVICES AND AUTOMATION CAPABILITIES.

![architecture.png](architecture.png)

### 2-APP AND IT’S DEPLOYMENT
#### REQUIREMENTS FOR THE CURRENCY CONVERTER WEB APP
A WEB-BASED CURRENCY CONVERTER THAT RELIES ON AN API TO FETCH REAL-TIME CURRENCY RATES.

1- SCALABILITY
2- AVAILABILITY
3- SECURITY
4- TRAFFIC MANAGEMENT

#### WHAT AND WHY WE CHOOSE THIS OPTION 
1. AZURE APP SERVICE: HOSTING PLATFORM
HERE’S WHY:
•PAAS BENEFITS
•COST EFFICIENCY
•MINIMAL MAINTENANCE REQUIRED AND HIGH PERFORMANCE WITH BUILT-IN SUPPORT FOR APIS.
•BUILT-IN SECURITY AND MONITORING

2. NAT GW: SECURING OUTBOUND TRAFFIC
HERE’S WHY:
•OUTBOUND SECURITY
•PUBLIC IP PROTECTION
•SCALABILITY

3. APPLICATION GATEWAY: MANAGING AND SECURING INBOUND TRAFFIC
HERE’S WHY:
•INBOUND TRAFFIC MANAGEMENT
•SSL TERMINATION
•WEB APPLICATION FIREWALL (WAF)
•SCALABILITY

4. NETWORK SECURITY GROUPS (NSGS): CONTROLLING NETWORK TRAFFIC
HERE’S WHY:
•GRANULAR TRAFFIC CONTROL
•LAYERED SECURITY
•COST EFFICIENCY

#### HOW IS THE DEPLOYMENT DONE?
•VIRTUAL NETWORK
•SUBNET WITH NSG
•NAT GATEWAY
•APPLICATION GATEWAY
•AZURE APP SERVICE

•USER REQUESTS: WHEN A USER ACCESSES THE APP, THEIR REQUEST GOES THROUGH THE APPLICATION GATEWAY.

•SSL Termination & WAF: The Application Gateway terminates the SSL connection, inspects traffic for security vulnerabilities using WAF, and then routes it to the app instances.

•App Processing: The web app handles the request and sends the response back via the Application Gateway.

•Outbound Protection: Any potential outbound traffic is securely routed through the NAT Gateway, preventing exposure of the app’s internal IPs

![app architecture.png](apparchitecture.png)

### 3. DATABASE MIGRATION
#### WHY MIGRATE THE DATABASE TO AZURE?
1. SCALABILITY
2. Reliability
3. Reduced Maintenance Costs
4. Cost Optimization
5. Compliance and Security
6. Integration with Existing Infrastructure

#### WHAT ARE THE AVAILABLE SOLUTIONS?
##### SQL virtual machines
Best for migrations and applications requiring OS-level access
##### Managed instances
Best for most lift-and-shift migrations to the cloud
##### SQL Databases
Best for modern cloud applications

#### WHAT AND WHY WE CHOSE THIS OPTION
**AZURE SQL DATABASE**: IS THE RECOMMENDED SOLUTION.
**HERE’S WHY:**
• PAAS BENEFITS

• COST EFFICIENCY

• BUILT-IN SECURITY AND COMPLIANCE

• INTEGRATION WITH BLOB STORAGE FOR ARCHIVAL

![on prem.png](onprem.png)

#### HOW IS THE DEPLOYMENT DONE?
**DATABASE MIGRATION VIA SSMS (SQL SERVER MANAGEMENT STUDIO):**
THE PROCESS INCLUDED EXPORTING THE ON-PREMISES SQL DATABASES AND IMPORTING THEM DIRECTLY INTO AZURE SQL DATABASE.

**BLOB STORAGE SETUP FOR ARCHIVING:**
• BLOB CONTAINER IS USED TO AUTOMATICALLY MOVE OLD DATA FROM OUR DATABASES TO A CHEAPER STORAGE PLACE.

• THIS SOLUTION IS COST-EFFICIENT COSTS.

• OLD DATA IS ACCESSIBLE IF NEEDED.

you can **click the link** below to see a demo of the implementation 

https://drive.google.com/file/d/1kVHk32geUAJIaJTUdjqju9UU-n85wa5A/view?usp=sharing

