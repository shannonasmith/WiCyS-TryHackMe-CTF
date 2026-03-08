<div align="center">

# 🏁 WiCyS / TryHackMe Tier 2 CTF

## 🧠 Advanced Security Investigation Portfolio

![Event](https://img.shields.io/badge/Event-WiCyS%20CTF-6A0DAD?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Web%20Security%20%7C%20Forensics%20%7C%20OSINT-blue?style=for-the-badge)
![Approach](https://img.shields.io/badge/Approach-Investigation%20First-success?style=for-the-badge)

</div>

---

## 🎯 Objective

This CTF expanded on the investigative techniques developed during the **WiCyS / SANS Beginner-Level CTF** by introducing more complex artifacts, deeper system analysis, and multi-step problem solving.

Rather than focusing only on solving challenges, each task was approached as a **structured security investigation**.

The goals of this Tier 2 event were to:

* 🔁 Apply structured investigative workflows to more complex systems
* 🔍 Analyze attacker artifacts across multiple domains
* 🧾 Strengthen forensic artifact reconstruction skills
* 🧭 Practice analytical pivoting when investigative paths fail
* 📚 Continue building a documented repository of security investigation techniques

All writeups focus on **methodology, reasoning, and investigative workflow**.

To respect competition integrity:

* ❌ Flags are not published
* ❌ Protected answers are not disclosed
* ✔ Only investigative techniques and analysis are documented

---

# 🛠 Technical Domains Practiced

| Domain                   | Focus Area                                                 |
| ------------------------ | ---------------------------------------------------------- |
| 🌐 Web Security          | Input manipulation, parameter tampering, command injection |
| 🔐 Cryptography          | Encoding analysis, hashing, RSA decryption                 |
| 📄 Digital Forensics     | Artifact inspection, data recovery, layered archives       |
| 🧠 OSINT Investigation   | Social media analysis, geolocation, public intelligence    |
| 🔍 Reverse Engineering   | Program behavior inspection and analysis                   |
| 🖼 Steganography         | Hidden data extraction from files                          |
| 📡 Network Investigation | Packet capture analysis and traffic reconstruction         |
| 🐧 Linux Security        | File system investigation and privilege escalation         |

---

# 🧩 Documented Challenges

---

## 🌐 Web Application Security

### **Endpoint**

🔎 [View Writeup](./endpoint)

* Investigated application behavior through endpoint enumeration
* Analyzed server responses to identify exposed functionality
* Demonstrated risks of improperly protected endpoints

---

### **Notepad Online**

🔎 [View Writeup](./notepad-online)

* Investigated a web-based note storage system
* Manipulated request parameters to test authorization controls
* Demonstrated an **Insecure Direct Object Reference (IDOR)** vulnerability

---

### **Scanner**

🔎 [View Writeup](./scanner)

* Analyzed application scanning functionality
* Investigated server responses to determine backend behavior
* Identified weaknesses in how the application processed user input

---

### **Time Travel**

🔎 [View Writeup](./time-travel)

* Investigated historical application states and responses
* Identified hidden information within previous versions of application content
* Demonstrated the value of analyzing **application history**

---

### **Arcanum**

🔎 [View Writeup](./arcanum)

* Explored hidden functionality within a web application
* Identified unexpected server responses through manual testing
* Demonstrated investigative enumeration techniques

---

### **What Does the Cow Say?**

🔎 [View Writeup](./what-does-the-cow-say)

* Tested user input fields for command injection behavior
* Executed shell commands through unsanitized application input
* Demonstrated server-side command execution vulnerabilities

---

### **The Sequel**

🔎 [View Writeup](./the-sequel)

* Investigated application responses for hidden data exposure
* Identified vulnerabilities through input manipulation
* Demonstrated how improper validation can expose sensitive information

---

## 🔐 Cryptography

### **B4sed**

🔎 [View Writeup](./b4sed)

* Identified layered encoding schemes within provided data
* Applied decoding techniques to recover hidden information
* Demonstrated the importance of identifying encoding patterns

---

### **Exam**

🔎 [View Writeup](./exam)

* Investigated encoded challenge content
* Applied cryptographic analysis to recover hidden data
* Demonstrated structured decoding methodology

---

### **Exam 2**

🔎 [View Writeup](./exam-2)

* Analyzed password hashing techniques
* Generated candidate passwords using rule-based mutation
* Demonstrated hash cracking methodology

---

### **Exam 3**

🔎 [View Writeup](./exam-3)

* Investigated RSA encryption implementation
* Identified weaknesses allowing key recovery
* Demonstrated practical cryptographic exploitation techniques

---

## 📄 Digital Forensics

### **CrackMyPass 1**

🔎 [View Writeup](./crackmypass1)

* Investigated hashed password artifacts
* Applied cracking techniques to recover credentials
* Demonstrated password security weaknesses

---

### **CrackMyPass 2**

🔎 [View Writeup](./crackmypass2)

* Generated password candidates through rule-based mutation
* Applied automated cracking techniques using hashcat
* Demonstrated the effectiveness of mutation-based attacks

---

### **CrackMyPass 3**

🔎 [View Writeup](./crackmypass3)

* Identified unknown hashing algorithm
* Applied hash identification techniques
* Recovered password through targeted cracking methods

---

### **Stolen Footprints**

🔎 [View Writeup](./stolen-footprints)

* Investigated packet capture artifacts
* Identified attacker file retrieval using FTP commands
* Reconstructed the stolen file through TCP stream analysis

---

### **Mayhem**

🔎 [View Writeup](./mayhem)

* Investigated network artifacts contained in forensic evidence
* Identified encrypted attacker command-and-control traffic
* Reconstructed attacker communication through artifact analysis

---

## 🧠 OSINT Investigation

### **Eggciting Recovery**

🔎 [View Writeup](./eggciting-recovery)

* Investigated public data sources for hidden information
* Applied OSINT research techniques to identify relevant artifacts

---

### **FooTPrints**

🔎 [View Writeup](./footprints)

* Investigated digital traces left by an attacker
* Correlated open-source information to identify relevant evidence

---

### **TryFindMe**

🔎 [View Writeup](./tryfindme)

* Performed reverse image search to determine image location
* Correlated OSINT sources to verify geographic location
* Demonstrated practical image geolocation techniques

---

### **Operation Slither 1**

🔎 [View Writeup](./operation-slither)

* Investigated social media activity of a suspected threat actor
* Identified encoded messages hidden within public posts
* Recovered hidden information through data decoding

---

## 🖼 Steganography

### **Chat Bubble**

🔎 [View Writeup](./chat-bubble)

* Investigated a suspicious image file
* Identified embedded data within the artifact
* Extracted hidden content using forensic analysis techniques

---

## 📡 Network Investigation

### **Packet Inspector**

🔎 [View Writeup](./packet-inspector)

* Analyzed network packet captures using Wireshark
* Identified suspicious communication patterns
* Reconstructed attacker activity from captured traffic

---

### **Strange Beacon**

🔎 [View Writeup](./strange-beacon)

* Investigated abnormal network communication
* Identified beaconing behavior consistent with command-and-control activity

---

## 🐧 Linux Security

### **Get That Flag Out**

🔎 [View Writeup](./get-that-flag-out)

* Investigated a misconfigured SUID binary
* Demonstrated privilege escalation through binary abuse
* Highlighted risks of improper permission management

---

### **Archives**

🔎 [View Writeup](./archives)

* Investigated nested archive artifacts
* Identified multiple compression layers with altered file extensions
* Recovered hidden data through systematic archive extraction

---

# 🧠 Key Takeaways

* Authorization flaws can expose sensitive data even when authentication is present
* File signatures provide more reliable format identification than file extensions
* OSINT investigations can reveal attacker behavior through public activity
* Misconfigured Linux permissions often lead to privilege escalation vulnerabilities
* Layered archives and encoded data are common techniques for hiding information
* Structured investigative documentation improves analytical clarity

---

<div align="center">

## 👤 Shannon Smith

Cybersecurity | DFIR • Web Security • Threat Analysis
U.S. Navy Veteran | Virginia Tech — M.S. Information Technology

🛡️ Thinking like an analyst
🔎 Documenting investigations
📈 Building repeatable security workflows

</div>
