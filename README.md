# ItsyBitsy


# Project Report: Investigating a Potential Command-and-Control (C2) Communication Alert

![image](https://github.com/user-attachments/assets/f38d3b1f-fe72-48bd-85e5-1ee04b068978)

### 1. Overview

This project involves investigating a potential Command-and-Control (C2) communication alert within a simulated network environment provided by TryHackMe (THM). The investigation was conducted as part of my ongoing learning in cybersecurity, specifically focusing on threat detection and incident response. The primary objective was to analyze logs and network traffic using the tools and techniques learned in previous modules and to answer specific questions related to the potential C2 communication.

### 2. Task 2 Scenario — Investigate a Potential C2 Communication Alert

The scenario began by connecting to the THM network via OpenVPN on my Kali Linux machine. Partial directions for connecting to the network were provided in my Remote Desktop Protocol (RDP) room. Once connected, I opened a browser and accessed the machine's IP address, which in this instance was 10.10.34.200. The investigation was structured around answering a series of questions that guided the analysis process.

### 2.1 How many events were returned for the month of March 2022?

To determine the number of events returned for March 2022, I accessed the "Discover" page in the ElasticSearch, Logstash, and Kibana (ELK) Stack by clicking on the hamburger icon. I then adjusted the date filter on the top right to match the required criteria. After updating the results, the system returned 1,482 events for the specified period.

![image](https://github.com/user-attachments/assets/bacf0a52-af3f-46cd-b76b-8d344f6b680e)

![image](https://github.com/user-attachments/assets/fd25b5f5-a5dd-497f-95cd-3b114674d98b)

![image](https://github.com/user-attachments/assets/ec0e4b01-88f2-4336-bfd9-6eea4fa506fc)

    Answer: 1482

### 2.2 What is the IP associated with the suspected user in the logs?

Using the results from the previous query, I filtered the logs by the "source_ip" field to identify the IP addresses associated with the suspected user. Two IP addresses appeared in the logs, and after evaluating them, I identified the correct one.

![image](https://github.com/user-attachments/assets/b3ec8a48-7e48-444e-83a1-8dab99b26c77)


    Answer: 192.166.65.54

### 2.3 The user’s machine used a legit Windows binary to download a file from the C2 server. What is the name of the binary?

To identify the binary used by the user's machine, I applied a filter to the logs, searching for "GET" requests associated with the identified IP address. The log showed that the binary used was bitsadmin, a legitimate Windows command-line tool for downloading files.

![image](https://github.com/user-attachments/assets/9018ef7e-9ccf-49f2-a353-b4eb6ead912a)


    Answer: bitsadmin

### 2.4 The infected machine connected with a famous file-sharing site in this period, which also acts as a C2 server used by the malware authors to communicate. What is the name of the file-sharing site?

The investigation revealed that the infected machine connected to pastebin.com, a well-known file-sharing site that is also utilized by malware authors as a C2 server.

![image](https://github.com/user-attachments/assets/6f6cc76f-445f-43a9-9ecc-7e7d61b3ef06)


    Answer: pastebin.com

### 2.5 What is the full URL of the C2 to which the infected host is connected?

By examining the same log result further, I identified the full URL of the C2 server. The combination of the site and the URI gave me the final URL.

![image](https://github.com/user-attachments/assets/ba905acf-c7f0-44b1-9348-f8743ecbbc5c)


    Answer: pastebin.com/yTg0Ah6a

### 2.6 A file was accessed on the file-sharing site. What is the name of the file accessed?

To find the name of the accessed file, I navigated to the URL identified in the previous step. Upon reaching the page, I found the file named secret.txt.

![image](https://github.com/user-attachments/assets/6e77654a-b465-497c-b38a-6c5150ef2555)

![image](https://github.com/user-attachments/assets/4b1fc3ee-1433-464d-b19d-8a6ab01a7897)



    Answer: secret.txt

### 2.7 The file contains a secret code with the format THM{_____}.

Upon opening the secret.txt file, I found a secret code embedded within it, formatted as THM{SECRET__CODE}.

    Answer: THM{SECRET__CODE}

### 3. Thoughts

This exercise was a valuable learning experience in analyzing potential C2 communication alerts. While I found the tasks relatively straightforward, they reinforced key concepts in log analysis and threat detection. I made an error in initially choosing the wrong IP address due to its higher presence, which highlighted the importance of critical thinking in cybersecurity investigations. Although I will not be immediately pursuing the next Splunk rooms (as I have completed them before), I plan to revisit them in the future to refresh my skills and complete the SOC Level 1 learning path. The next area of focus in my learning journey will be forensics, where I will continue to build my expertise in cybersecurity.
4. Conclusion

This project provided practical insights into detecting and analyzing C2 communications within a network, an essential skill for any cybersecurity professional. Through hands-on investigation and log analysis, I was able to identify key indicators of compromise and understand how threat actors utilize legitimate tools and services for malicious purposes. The knowledge and experience gained from this exercise will be instrumental as I continue to develop my skills in cybersecurity and prepare for more advanced challenges in the field.
