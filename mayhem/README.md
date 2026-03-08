<div align="center">

# 💥 Mayhem  
## DFIR Investigation & Havoc C2 Traffic Decryption

![Category](https://img.shields.io/badge/Category-Digital%20Forensics-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-C2%20Traffic%20Decryption-blue?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-Network%20Forensics-success?style=for-the-badge)

</div>

---

### 🎯 Objective

Investigate a captured forensic dataset containing evidence of attacker activity.

The challenge description suggested that attacker activity was hidden within the evidence archive. The goal was to analyze the provided artifacts to determine how the attacker communicated with their command-and-control (C2) infrastructure and what information was retrieved.

The investigation focused on identifying encrypted attacker communications and recovering the information contained within them.

---

### 🖥 Environment

| Tool | Purpose |
|-----|------|
| Kali Linux AttackBox | Investigation environment |
| `wget` | Retrieve forensic evidence |
| `unzip` | Extract artifacts |
| Wireshark | Network traffic analysis |
| Terminal | Command execution and analysis |

---

### 📦 Step 1 — Retrieve the Evidence

The investigation began by downloading the evidence archive from the provided location.

```bash
wget http://10.10.133.71/evidence.zip
```

After downloading the archive, the working directory was inspected to identify the available artifacts.

```bash
ls
```

📸 **Forensic Artifacts Provided**

<img src="../images/image046.png" width="600">

The directory contained several files relevant to the investigation, including:

- `evidence.zip` — archive containing investigation artifacts  
- `traffic.pcapng` — packet capture of attacker activity  

These files served as the starting point for reconstructing the attacker’s actions.

---

### 🔍 Step 2 — Extract the Investigation Artifacts

The evidence archive was extracted to reveal the files contained inside.

```bash
unzip evidence.zip
```

Digital forensic investigations typically begin by reviewing all available artifacts to determine which files contain relevant evidence.

Artifacts often include:

- packet captures  
- logs  
- attacker tools  
- suspicious files  

These artifacts help investigators reconstruct attacker activity.

---

### 🧪 Step 3 — Analyze Network Traffic

The packet capture was opened using Wireshark to analyze the network activity recorded during the attack.

```bash
wireshark traffic.pcapng
```

Packet captures allow investigators to inspect communications between systems and identify suspicious activity.

During analysis, encrypted traffic associated with attacker communication was identified.

Further investigation revealed that the attacker was using **Havoc C2**, a red-team command-and-control framework.

---

#### 🔎 Analytical Observation

Command-and-control frameworks commonly encrypt their communications to prevent defenders from easily reading attacker commands.

However, forensic analysis can sometimes reveal the **encryption parameters used by the attacker**, which allows investigators to decrypt captured communications and reconstruct attacker behavior.

---

### 🔄 Step 4 — Recover the Encryption Parameters

Through analysis of the artifacts, the encryption key and initialization vector used by the attacker were recovered.

```
946cf2f65ac2d2b868328a18dedcc296cc40fa28fab41a0c34dcc010984410ca8cd00c3e349290565aaa5a8c3aacd430
```

These values allowed the encrypted communication to be decrypted and analyzed.

---

### 🔐 Step 5 — Reconstruct the Attacker Activity

After identifying the encryption parameters, the attacker’s communication could be decrypted.

This revealed that the attacker had printed a message containing a flag, confirming that the encrypted traffic contained useful forensic evidence.

Further investigation of the artifacts also revealed an additional file accessed by the attacker, which contained the final hidden message.

---

## 🧠 Methodology Framework Applied

```
Evidence archive obtained
      ↓
Artifacts extracted
      ↓
Network traffic analyzed
      ↓
C2 framework identified
      ↓
Encryption parameters recovered
      ↓
Attacker communication decrypted
      ↓
Incident activity reconstructed
```

---

## 🛠 Techniques Used

Primary techniques used:

- digital forensic artifact analysis  
- packet capture investigation  
- command-and-control identification  
- encrypted traffic analysis  
- incident reconstruction  

Key concept investigated:

```
C2 traffic decryption
```

---

## 🛡 Defensive Insight

Attackers frequently use command-and-control frameworks to maintain persistent access and issue commands to compromised systems.

Even when attacker communications are encrypted, forensic investigations can sometimes recover encryption parameters and reconstruct the attacker’s actions.

Organizations should implement:

- network monitoring and intrusion detection systems  
- endpoint detection and response (EDR)  
- anomaly detection for unusual traffic patterns  
- strong incident response procedures  

These measures help detect and investigate malicious command-and-control activity.

---

## 💡 Skills Reinforced

- Digital forensics investigation  
- Network traffic analysis  
- C2 framework identification  
- Encrypted traffic investigation  
- Incident reconstruction  

---

<div align="center">

💥 Even encrypted traffic leaves forensic evidence  
🔍 Investigations reveal attacker infrastructure  
🧠 DFIR analysis reconstructs attacker behavior  

</div>
