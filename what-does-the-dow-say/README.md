<div align="center">

# 🐄 What Does the Cow Say  
## Command Injection & Shell Interaction Analysis

![Category](https://img.shields.io/badge/Category-Web%20Security-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Command%20Injection-blue?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-Input%20Manipulation-success?style=for-the-badge)

</div>

---

### 🎯 Objective

Analyze a PHP web application and determine whether user input can influence the system commands executed by the server.

The challenge involved interacting with a simple web interface and identifying whether backend command execution could be manipulated through crafted input.

The goal was to determine if the application was vulnerable to **command injection**, allowing an attacker to execute arbitrary shell commands.

---

### 🖥 Environment

| Tool | Purpose |
|-----|------|
| Web browser | Application interaction |
| Kali Linux AttackBox | Testing environment |
| Browser input field | Injection testing |
| Linux commands | Server file enumeration |

---

### 📦 Step 1 — Access the Application

After starting the challenge machine, the target web application was accessed through the provided IP address.

```
http://10.10.x.x
```

The page contained a simple form that accepted user input and returned a response.

Given the nature of the challenge description, the next step was to determine whether the input field interacted with system commands on the backend.

---

### 🔍 Step 2 — Test Command Injection

To determine whether the input field was vulnerable to command injection, a command substitution payload was entered into the form.

```bash
$(ls)
```

If the application executed the input within a shell context, this command would return a directory listing.

📸 **Server Directory Listing**

<img src="../images/image012_redacted.png" width="600">

The response revealed several server-side files:

```
css
flag-[redacted].txt
index.php
js
```

The presence of the flag file confirmed that **the application was executing user input as part of a shell command**.

---

### 🧪 Step 3 — Retrieve the Target File

After identifying the flag file from the directory listing, the next step was to read its contents.

The following command injection payload was submitted:

```bash
$(cat flag-[redacted].txt)
```

📸 **File Contents Retrieved**

<img src="../images/image013_redacted.png" width="600">

The server executed the injected command and returned the contents of the file in the HTTP response, confirming that arbitrary commands could be executed through the vulnerable input field.

---

#### 🔎 Analytical Observation

Command injection vulnerabilities occur when applications pass user input directly into system commands without proper validation.

Attackers can exploit this behavior by inserting shell commands using techniques such as:

- command substitution
- command chaining
- shell metacharacters

This allows attackers to interact directly with the underlying operating system.

---

### 🔐 Step 4 — Confirm Command Execution

The successful execution of both injected commands demonstrated that the application failed to sanitize user input before passing it to the system shell.

This confirmed that the application was vulnerable to **command injection**, allowing attackers to execute arbitrary system commands on the server.

---

## 🧠 Methodology Framework Applied

```
Web application access
      ↓
Input field testing
      ↓
Command substitution payload
      ↓
Directory enumeration
      ↓
File discovery
      ↓
Command execution to retrieve contents
```

---

## 🛠 Techniques Used

Primary techniques used:

- command injection testing  
- shell command substitution  
- server-side file enumeration  
- input validation analysis  

Key concept investigated:

```
Command Injection
```

---

## 🛡 Defensive Insight

Command injection vulnerabilities occur when applications execute user-supplied input within system commands without proper sanitization.

Secure development practices include:

- validating user input  
- sanitizing shell metacharacters  
- avoiding direct shell execution  
- using parameterized command execution methods  

Without proper input validation, attackers may execute arbitrary system commands and potentially gain full system access.

---

## 💡 Skills Reinforced

- Web application vulnerability analysis  
- Command injection detection  
- Server-side command execution behavior  
- Directory enumeration through shell commands  
- Input validation awareness  

---

<div align="center">

🐄 Never trust user input  
🔎 Test how applications process shell characters  
🧠 Command injection can expose entire systems  

</div>
