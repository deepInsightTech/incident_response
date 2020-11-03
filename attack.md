## Attack Surface
 
1. Data Breach
   1. Steps
      1. Activate the IRT (Incident Response Team)
          IRT includes
         1. An executive with decision making authority
         2. 'First Responder' DevOps and Team Lead with access to system.
         3. CTO
      2. Established 'privileged' reporting and communication channel
         1. (Ideally before the breach) Maintain the confidentiality of the investigation
         2. Legal counsel should recieve all incident reports
      3. Use of independent cyber security and forensic experts (*if required)
      4. Stop additional data loss
         1. Usage of tools to dynamically image affected systems to preserve evidence prior taking systems offline by disconnecting them from the network. (Possible becuase of system built on Event Driven Architecture)
      5. Secure evidence
         1. Secure and prevent physical access to affected system to maintain the integrity of the evidence
         2. Preserve all security access devices (tokens) logs and surveillance tapes
         3. Determine
            1. Who had contact with affected system?
            2. What did they do?
            3. Who was the next to touch the affected system?
      6. Preserve computer logs
         1. Presrve all affected system log files including firewall, VPN, network, webserver, IDS logs
         2. These logs are critical to assess the origin of the attack, its duration and the volume of data exfiltrated during the breach
      7. Document the Data Breach
         1. data, time of the breach
         2. the personnel who discovered the breach
         3. the kinds of data stolen/lost
         4. All employees who access to the affected systems
         5. Document all data/ or devices affected in the breach
      8. Interview personnel involved
      9. Change security access devices and passwords
   2.  Case Study
       1.  Data of over 7 million BHIM users exposed
           1.  Root Cause - S3 bucket misconfiguration, PII leaked
               1.  Aadhar Card Details
               2.  Residence proof
               3.  Bank records
           2. Truecaller - Data of 4.75 corer Indians Dark Web
              PII leaked: 
              1. Username, gender, age
              2. Facebook account
              3. Email ID
              4. Mobile number

2. Cloud
   1. Challenges
      1. Traffic filtering and logs
      2. Log retention period
      3. Access Management
      4. Insecure Host Configurations
   2. Technologies
      1. AWS
         1. Monitoring toolsets
            1. IAM Policy
            2. Cloudwatch
            3. VPCFlow logs - Feature that enanles to caputre information about the IP traffic going to and from network interfaces in VPC
            4. CloudTrail - Services that enables governance, compliance, operational auditing and risk auditing of AWS account
            5. Gauardduty
         2. Incident Domains
            1. Service
               1. AWS account
               2. IAM Permissions
               3. Billing
            2. Infrastructure - It includes data or network related activity eg Traffic to your Amazon EC2 instances with VPC
            3. Application - Related to application code or application deployed in the infra

3. Phishing Attack
   1. Analysis
      1. The Form Field: Contains the name of the sender
      2. X-Authenticated User: Contains the Email Address of the sender
      3. Usage of MX-Toolbox for Header Analysis 
      4. *Deployment of AV signature to the endpoints
   2. Case Study
      1. COVID-19 Related phising attacks

4. Malware
   1. Steps
      1. Suspect the file and generate the MD5 hash & send it to malwareDB
      2. If its unknown malware then send for sandbox for analysis
      3. Check for Encryption capabilities then scan for Crypto Malware processes and files
      4. Scan other systems for the same malware type
      5. Identify the source and block from Firewall
      6. Recover files from Backup
   2. Analysis
      1. Get HASH and check on virustotal.com
      2. Use PeStudio for Static Analysis
      3. Monitor process
         1. Process Hacker
            1. While execution check the strings from the memnory of the process
            2. Checking of Handles tab
         2. Process Monitor
      4. ProcDot - To get a good diagrammatic representation
      5. totalhash.com
      6. urlvoid.com - Website reputation checker
      7. dnSpy - used for reverse engineering
      8. Remnux, FLARE - OS specific for Malware Analysis
      9. fakedns - used for behaviour analysis of malware
      10. Retrohunt - Allows us to scan all the files sent to VirusTotal in the past 12 months with your YARA rules - [a way of identifying malware (or other files) by creating rules that look for certain characteristics]
   3. Case Study
      1. Implementation on Decoys to identify the attach of Mirai Botnet
      2. Detection of WannCry - Attacking SMB and Eternalblue exploit
      3. Crypto mining Malware
         1. PyRoMine
         2. Adylkuzz
            1. Exploiting the MS17-010 SMB like WannaCry but less noisy
            2. Unique feature - Prevent system to infect from other malwares which tries to exploit MS17-010
            3. Uses LUA language

5. DDoS Attack
   1. Steps
      1.  Proactive Measures
          1.  Usage of Firewall botnet filter and monitor for outgoing traffic
          2.  Check for IRC, P2P protocols
          3.  Usage of Network Monitoring utility like - LANGuardian to identify traffic patterns
          4.  Disaable DNS recursive queries
          5.  Review the load and log files of affected systems
          6.  Contact ISP to provide details about traffic sources like source IP addresses, Protocols
      2. Identification
         1. Increase in the volume of traffic
         2. Consistent increase in bandwidth utilization
         3. Alters from the Botnet Filter (AWS WAF Classic)
         4. Abnormal increase in DNS lookups failures
      3. Containment
         1. Allow only whitelisted IPs for production push and connect
         2. Block the IPs identified as sending throttle traffic
         3. Block the suspicious range of IP addresses and multiple cnnection requests for the same source
      4. Eradication
         1. Route traffic through traffic-scrubbing service or product via routing changes (eg sinkhole routing). Usage of Squid, a leading open-source proxy, to implement a “transparent proxy”
         2. Configure egress filters to block the traffic which your system may send in response to DDoS

6. Network related attacks
   1. Linux operating system stores a timeline of events and analysis of network related logs can be used to detect attack
   
      