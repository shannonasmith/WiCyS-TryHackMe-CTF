<div align="center">

# 🔓 CrackMyPass 2  
## Rule-Based Password Generation & MD5 Hash Cracking

![Category](https://img.shields.io/badge/Category-Cryptography-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Hash%20Cracking-blue?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-Rule_Based_Mutation-success?style=for-the-badge)

</div>

---

### 🎯 Objective

Analyze a leaked MD5 password hash and recover the original password using contextual clues and rule-based candidate generation.

The challenge specified that the password was based on the company name **krakencorp**, but could not be recovered using standard password dictionaries alone.

The objective was to generate likely password mutations from the base company name and test them against the provided MD5 hash.

---

### 🖥 Environment

| Tool | Purpose |
|-----|------|
| Kali Linux AttackBox | Testing environment |
| Hashcat | Rule-based candidate generation and hash cracking |
| Bash | Automating rule application |
| `grep` | Filtering generated candidates by length |

---

### 📦 Step 1 — Inspect the Hash and Clue

The challenge provided the following MD5 hash:

```text
2988d581dce57afa7c60ee86e74d576f
```

It also included a key hint:

```text
The password was based on the company name krakencorp.
```

Because the hash was identified as **MD5**, the investigation focused on recovering the original password by generating likely mutations of the base word rather than relying on generic wordlists.

---

### 🔍 Step 2 — Use the Company Name as a Base Word

The company name `krakencorp` was used as the starting point for password generation.

Since standard dictionaries did not appear sufficient, the next step was to apply **Hashcat rule files** to mutate the base word into more realistic password candidates.

These rule files simulate common user password behaviors such as:

- capitalization changes  
- character substitutions  
- appended punctuation  
- other predictable transformations  

---

### 🧪 Step 3 — Generate Candidate Passwords with Hashcat Rules

A Bash script was used to apply every rule file in `/usr/share/hashcat/rules/` to the base word and save matching candidates to a custom wordlist.

The generated passwords were filtered to retain only strings that were exactly **11 characters long**, narrowing the candidate space.

```bash
#!/bin/bash

# Starting word (krakencorp)
base_word="krakencorp"

# Output file to save the generated passwords
output_file="crackedpasswords.txt"

# Loop over all the rules in /usr/share/hashcat/rules/
for rule in /usr/share/hashcat/rules/*.rule; do
    # Apply each rule and append the result to crackedpasswords.txt
    echo -n "$base_word" | hashcat --stdout -r "$rule" | grep -E '^.{11}$' >> "$output_file"
done

echo "Password generation complete. Check $output_file."
```

This process created a focused password list derived from the company name using realistic user-style mutations.

---

#### 🔎 Analytical Observation

This challenge demonstrates the effectiveness of **rule-based password cracking**.

Rather than brute forcing from scratch, the workflow used:

- a known base word  
- common transformation rules  
- a constrained output length  

This dramatically reduced the search space and mirrored how attackers leverage **context and mutation rules** to recover passwords efficiently.

---

### 🔄 Step 4 — Test the Generated Candidates Against the MD5 Hash

Once the custom candidate list was generated, Hashcat was used to test those passwords against the provided MD5 hash.

```bash
hashcat -m 0 -a 0 2988d581dce57afa7c60ee86e74d576f crackedpasswords.txt
```

This command instructed Hashcat to:

- use **MD5 mode** (`-m 0`)  
- perform a **straight dictionary attack** (`-a 0`)  
- compare the provided hash against the generated candidate passwords  

The cracking process successfully identified a matching password from the custom wordlist.

---

### 🔐 Step 5 — Confirm Password Recovery

The hash was successfully matched to a password generated from the company-name-based candidate set.

This confirmed that the password could not be recovered easily through standard dictionaries, but became crackable once **context-aware rule mutations** were applied.

The investigation showed how predictable password construction patterns can undermine password security even when direct lookup methods fail.

---

## 🧠 Methodology Framework Applied

```text
MD5 hash provided
      ↓
Company-name clue identified
      ↓
Base word selected
      ↓
Hashcat rule mutations applied
      ↓
Custom wordlist generated
      ↓
Hash matched and password recovered
```

---

## 🛠 Techniques Used

Primary techniques used:

- MD5 hash identification  
- rule-based password mutation  
- custom wordlist generation  
- Hashcat dictionary attack  

Key concept investigated:

```text
Rule-based password cracking
```

---

## 🛡 Defensive Insight

Users often create passwords by applying small modifications to familiar words such as company names, brands, or internal terminology.

Attackers exploit this behavior using **rule-based mutation engines** that can generate thousands of realistic password variations quickly.

Secure password practices should include:

- random password generation  
- password managers  
- strong password hashing algorithms  
- unique salts for each password  

Predictable password construction makes even non-trivial passwords vulnerable to targeted cracking workflows.

---

## 💡 Skills Reinforced

- MD5 hash analysis  
- Hashcat rule-based candidate generation  
- Custom wordlist creation  
- Context-aware password cracking  
- Understanding password mutation patterns  

---

<div align="center">

🔓 Context clues make password cracking faster  
🔍 Rule-based mutations mimic real user behavior  
🧠 Predictable passwords are vulnerable even without direct lookup  

</div>
