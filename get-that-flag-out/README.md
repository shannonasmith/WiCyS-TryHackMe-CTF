<div align="center">

# 🚩 Get That Flag Out  
## Linux Privilege Escalation & SUID Misconfiguration Exploitation

![Category](https://img.shields.io/badge/Category-Linux%20Security-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Privilege%20Escalation-blue?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-SUID%20Abuse-success?style=for-the-badge)

</div>

---

### 🎯 Objective

Investigate a Linux system where an application has been configured with the **SUID (Set User ID) bit**.

The challenge description suggested that the application had been incorrectly configured to run with elevated privileges.

The objective was to determine whether the SUID configuration could be abused to access a restricted file owned by the root user.

---

### 🖥 Environment

| Tool | Purpose |
|-----|------|
| Kali Linux AttackBox | Investigation environment |
| Linux terminal | Command execution |
| `file` | Inspect binary information |
| SUID misconfiguration | Privilege escalation |

---

### 📦 Step 1 — Identify the Suspicious Binary

The investigation began by inspecting the binary located in Johnny's home directory.

```bash
file /home/johnny/openvpn
```

The output confirmed that the file was an executable binary.

Because the challenge description mentioned SUID configuration, the next step was to determine whether the binary could be executed with elevated privileges.

---

### 🔍 Step 2 — Understand the SUID Risk

The **SUID bit** allows a program to run with the permissions of the file owner rather than the user executing it.

If the file owner is **root**, any user who runs the binary effectively executes it with root privileges.

Misconfigured SUID binaries can therefore allow attackers to:

- escalate privileges
- access restricted files
- execute privileged commands

This makes SUID misconfigurations a common privilege escalation vector.

---

### 🧪 Step 3 — Attempt to Abuse the Binary

Because the openvpn binary had elevated permissions, it could potentially be abused to access restricted files.

The binary was executed with the path to the protected file as an argument.

```bash
/home/johnny/openvpn /root/flag.txt
```

If the binary runs with root privileges, it will be able to access the file located inside the `/root` directory.

---

#### 🔎 Analytical Observation

Privilege escalation vulnerabilities often arise when applications are granted elevated permissions without sufficient safeguards.

Common risky configurations include:

- SUID-enabled binaries
- writable system files
- improperly restricted executables

Attackers frequently search for these conditions during post-exploitation to gain full system access.

---

### 🔐 Step 4 — Confirm Successful Privilege Escalation

Executing the binary successfully revealed the contents of the restricted file.

```
THM{[redacted]}
```

This confirmed that the SUID misconfiguration allowed the binary to access files owned by the root user.

---

## 🧠 Methodology Framework Applied

```
Suspicious binary identified
      ↓
Binary inspection performed
      ↓
SUID misconfiguration recognized
      ↓
Binary executed with elevated privileges
      ↓
Restricted file accessed
```

---

## 🛠 Techniques Used

Primary techniques used:

- Linux privilege escalation  
- SUID misconfiguration abuse  
- binary execution with elevated permissions  
- restricted file access  

Key concept investigated:

```
SUID privilege escalation
```

---

## 🛡 Defensive Insight

SUID misconfigurations can introduce serious privilege escalation vulnerabilities.

Applications should only be granted SUID privileges when absolutely necessary, and binaries with elevated permissions should be carefully audited.

Organizations should implement controls such as:

- regularly auditing SUID-enabled binaries  
- restricting executable permissions  
- monitoring for abnormal privilege escalation activity  

Proper privilege management reduces the risk of attackers gaining root access.

---

## 💡 Skills Reinforced

- Linux privilege escalation techniques  
- Identifying SUID misconfigurations  
- Understanding binary permission risks  
- Post-exploitation investigation  

---

<div align="center">

🚩 Misconfigured privileges can expose critical system files  
🔍 SUID binaries must be carefully controlled  
🧠 Privilege escalation often begins with small permission mistakes  

</div>
