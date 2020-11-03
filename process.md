# Process

1. Preparation
   1. Employees
      1. A skilled Response Team
      2. IT Security Training
   2. Documentation
      1. Well-defined policies
      2. Incident Communication Plan
      3. Chain of custody
   3. Defensive Measures
      1. AV (antivirus), HIDS (host-based intrusion detection system), NIDS (network intrusion detection system), DLP (Data Loss Prevention), EDR (Endpoint Detection and Response)
      2. SIEM (Security information and event management), UTM (Unified threat management), Threat Intelligence
      3. Central Logging, Honeypots, etc

2. Detection & Analysis
   1. Network Perimeter 
      1. Deployment of lightweight agents on EC2 instances for network traffic inspection. These agents mirror all traffic to virtual appliances that route suspicious packets through an encrypted channel to the cloud-hosted analytics platform.
   2. Host Perimeter
      1. Use of Amazon CloudWatch Logs to collect and aggregate alerts from an open-source security (OSSEC) HIDS. We use a CloudWatch Logs subscription to deliver the alerts to Amazon Elasticsearch Service (Amazon ES) for analysis and visualization with Kibana.
   3. Host Level
      1. Controlled access to DevOps
      2. A/Vs and EDR solutions help
      3. Example - User gets warned before running a malicious text.exe file (Since our hosting OS is linux, security audits help scan for malicious programs)
   4. Application Level
      1. Application logs, service Logs

3. Contaiment
   1. Usage of AWS Security features (eg: VPC) and use security solutions available on AWS Marketplace like CrowdStrike which provides unified technology for detection, response and forensics to stop breaches.
   2. Data Acquisition - Most volatile to the least
      Registers > CPU Cache > RAM > Persistent Storage
      1. Static
         1. Acquiring process of data which is non volatile (Data that will not be affected after a restart)
      2. Dynamic / Live
         1. Acquiring process of data which is volatile (Example: Object Instances in RAM)

4. Eradicate
   1. Indentify the root cause and indicators of compromise
   2. Removing backdoors or any other harmful artifacts
   3. Analyze logs to identify credential re-use
   4. Configuring additional router/firewall/Security group rules

5. Recovery
   1. Perform QA activities to ensure affected system is in the running condition
   2. Continue monitoring after it moved to the production
      1. Change to registry keys and values
      2. Abnormal user accounts
      3. Abnormal processes

6. Post-Incident Handling
   1. Learning Lessons as and when faced :) 
