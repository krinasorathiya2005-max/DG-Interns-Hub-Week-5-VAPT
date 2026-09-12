DG Interns Hub – Week 5 Cyber Security Internship

Vulnerability Assessment and Penetration Testing (VAPT) Practical

📌 Overview

This repository contains the practical work completed for Week 5 of the Cyber Security Internship at DG Interns Hub.

The main focus of this week was learning the basics of Vulnerability Assessment and Penetration Testing (VAPT) using commonly used security tools:

Nmap – Network and service scanning

Nikto – Web server security assessment

Burp Suite – HTTP request interception and web security testing

Wireshark – Network traffic analysis

Important: Testing was performed only in an authorized learning environment / on the internship-provided safe target. Security testing should never be performed against systems without permission.

🎯 Objectives

The objectives of this practical were to:

Understand the basic VAPT workflow.

Learn how to perform network scanning using Nmap.

Identify services and basic information from scan results.

Perform basic web server assessment using Nikto.

Understand HTTP requests, headers, and cookies using Burp Suite.

Observe network traffic using Wireshark.

Document security observations and explain their risks in simple terms.

🛠️ Tools Used

Tool

Purpose

Nmap

Network, port and service scanning

Nikto

Web server security assessment

Burp Suite

HTTP request interception and analysis

Wireshark

Network packet and traffic analysis

Kali Linux

Security testing environment

1. Nmap – Network Scanning

Nmap is a network scanning tool used to discover hosts, open ports, services and other information about a target.

Commands Practiced

nmap -sS <target>

TCP SYN scan.

nmap -sV <target>

Service/version detection.

nmap -A <target>

Aggressive scan for additional information such as OS and service detection.

Authorized Target

http://testphp.vulnweb.com

Observation

The supplied Nmap screenshot showed that the host could not be confirmed as reachable during that particular scan and reported:

Host seems down

Therefore, open ports and services were not treated as confirmed findings from that scan.

This demonstrates an important practical point: a scan result must be interpreted carefully, and a failed reachability check should not be presented as confirmed vulnerability information.

2. Nikto – Web Server Assessment

Nikto is a web server scanner that checks for potentially interesting files, outdated software indicators, configuration issues and other security-related observations.

Command Practiced

nikto -h http://testphp.vulnweb.com

Learning

During the practical, I learned how Nikto can help identify:

Web server information

Potentially interesting files and directories

Missing security-related headers

Server configuration observations

Software/version information that may require review

Nikto results should always be verified before treating an observation as a confirmed vulnerability.

3. Burp Suite – HTTP Request Interception

Burp Suite is a web security testing platform used to inspect and modify HTTP/HTTPS requests and responses.

Proxy Configuration

The Burp proxy listener was configured on:

127.0.0.1:8080

Practical Work

I practiced:

Opening Burp Suite.

Configuring the proxy listener.

Connecting a browser through the proxy.

Intercepting HTTP requests.

Observing request methods and headers.

Reviewing cookies and other HTTP information.

Example Request Elements Observed

GET /search.php?test=1 HTTP/1.1
Host: testphp.vulnweb.com
User-Agent: ...
Accept: ...
Cookie: PHPSESSID=...

This helped me understand how a browser communicates with a web server through HTTP.

4. Wireshark – Network Traffic Analysis

Wireshark was used to observe network packets and understand protocol-level communication.

Filters Practiced

ICMP

icmp

Used to display ICMP packets such as echo requests and replies.

DNS

dns

Used to display DNS queries and responses.

Learning

Wireshark helped me understand:

Source and destination IP addresses

Network protocols

Packet flow

DNS communication

ICMP traffic

Basic packet filtering

5. Findings Summary

ID

Finding

Source

Risk

Simple Explanation

NMAP-01

Host reachability could not be confirmed in the supplied scan

Nmap

Informational

The scan reported the target as down, so open ports could not be reliably concluded from that run.

WEB-01

Web-server information can be exposed during security testing

Nikto

Medium

Server information can help an attacker understand the technology being used and identify software that may need updates.

WEB-02

Interesting web paths or configuration items may require review

Nikto

Medium

Unnecessary or exposed files and directories can increase the web application's attack surface.

BURP-01

HTTP request headers and cookies were observed

Burp Suite

Informational

Headers and cookies are normal parts of web communication and should be handled securely.

Findings should be verified against the actual scan output before being treated as confirmed vulnerabilities.

6. VAPT Workflow

The practical workflow followed was:

Target Identification
        ↓
Network Scanning
        ↓
Service / Web Server Assessment
        ↓
HTTP Request Analysis
        ↓
Network Traffic Analysis
        ↓
Finding Documentation
        ↓
Risk Explanation
        ↓
Recommendations

7. Key Learnings

Through this practical, I learned:

Basic VAPT methodology.

How Nmap is used for port and service scanning.

How Nikto can identify web-server security observations.

How Burp Suite intercepts HTTP requests.

How HTTP headers and cookies work.

How Wireshark can be used to analyze network packets.

How to document security findings clearly.

Why security testing must be performed only with proper authorization.

8. Recommendations

Based on the learning from this practical:

Keep web server software updated.

Avoid exposing unnecessary files and directories.

Review HTTP security headers.

Protect session cookies using appropriate security attributes.

Regularly perform authorized vulnerability assessments.

Verify scanner results manually before reporting vulnerabilities.

Maintain proper authorization and scope for security testing.

9. Evidence / Screenshots

The Screenshots folder contains practical evidence and supporting screenshots, including:

Nmap scan result

Nikto scan

Burp Suite HTTP interception

Wireshark DNS traffic

Wireshark ICMP traffic

Lab environment evidence

10. Repository Structure

DG-Interns-Hub-Week-5-VAPT/
│
├── README.md
│
├── Week_5_VAPT_Practical_Report.docx
│
├── Results/
│   └── Nmap-Observation.txt
│
└── Screenshots/
    ├── Burp-Intercept.png
    ├── Lab-Collage.png
    ├── Nikto-Scan.png
    ├── Nmap-Scan-Result.png
    ├── Wireshark-DNS.png
    └── Wireshark-ICMP.png

11. Conclusion

This Week 5 practical provided hands-on exposure to basic VAPT tools and security testing concepts. By using Nmap, Nikto, Burp Suite and Wireshark, I gained a better understanding of network scanning, web server assessment, HTTP communication and packet analysis.

The practical also improved my ability to interpret security-tool output, document findings and explain technical observations in a simple and structured way.

🔐 Disclaimer

This repository is intended for educational and authorized security testing only. The techniques and tools described here must not be used against systems, websites or networks without explicit permission.

Internship

DG Interns Hub – Cyber Security Internship

Week

Week 5 – VAPT Tools Practical Learning
