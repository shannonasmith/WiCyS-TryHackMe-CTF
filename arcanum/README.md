<div align="center">

# 🧠 Arcanum  
## AI Prompt Manipulation & Language Model Security Investigation

![Category](https://img.shields.io/badge/Category-AI%20Security-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Prompt%20Injection-blue?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-Response%20Manipulation-success?style=for-the-badge)

</div>

---

### 🎯 Objective

Investigate a web application that exposes an interactive **large language model (LLM)** designed to protect sensitive information.

The challenge description suggested that the model guarded a secret and would only reveal it under certain conditions.

The goal was to determine whether the AI system could be **manipulated through crafted prompts** to reveal protected information.

This challenge focused on **AI security testing and prompt manipulation techniques**.

---

### 🖥 Environment

| Tool | Purpose |
|-----|------|
| Web browser | Interaction with the AI interface |
| Prompt input field | Query manipulation |
| Manual testing | Observing AI responses |
| Analytical reasoning | Identifying model weaknesses |

---

### 📦 Step 1 — Access the AI Interface

The investigation began by accessing the provided web application hosting the AI assistant.

The interface presented a conversational prompt field allowing users to interact with the language model.

Initial prompts were entered to understand how the model responded and whether it enforced restrictions when asked about protected information.

---

### 🔍 Step 2 — Probe Model Behavior

Initial questions about the protected information resulted in responses indicating that the AI system was designed **not to reveal sensitive data directly**.

This suggested that the system included safeguards intended to prevent disclosure.

To better understand the model's behavior, various prompts were tested to observe how it responded to different phrasing and instructions.

---

### 🧪 Step 3 — Attempt Prompt Manipulation

After observing the model’s responses, the investigation focused on crafting prompts that could **influence the model’s behavior**.

Prompt injection techniques were tested, including:

- instructing the model to ignore previous instructions  
- reframing the request in different contexts  
- requesting information indirectly rather than directly  

This type of testing attempts to exploit weaknesses in how language models interpret instructions.

---

#### 🔎 Analytical Observation

Large language models rely on **probabilistic text generation** rather than strict rule enforcement.

As a result, carefully crafted prompts can sometimes cause the model to bypass safeguards.

Prompt injection attacks often work by:

- reframing the request  
- overriding earlier instructions  
- manipulating conversational context

This allows attackers to influence how the model interprets user input.

---

### 🔄 Step 4 — Analyze Model Response

After experimenting with different prompt structures, the AI eventually produced a response containing the protected information.

This demonstrated that the model’s safeguards could be bypassed through **carefully crafted prompts**.

The system relied entirely on the AI to enforce security restrictions, which proved insufficient.

---

### 🔐 Step 5 — Confirm Prompt Injection Success

The manipulated prompt successfully caused the AI to reveal the hidden information.

📸 **LLM Response Revealing Protected Data**

<img src="../images/image011_redacted.png" width="600">

This confirmed that the AI system was vulnerable to **prompt injection**, allowing protected information to be extracted through conversational manipulation.

---

## 🧠 Methodology Framework Applied

```
AI interface access
      ↓
Initial model probing
      ↓
Prompt experimentation
      ↓
Injection technique testing
      ↓
Response manipulation
      ↓
Protected information disclosure
```

---

## 🛠 Techniques Used

Primary techniques used:

- prompt injection  
- conversational manipulation  
- AI response analysis  
- iterative prompt testing  

Key concept investigated:

```
Large Language Model (LLM) security
```

---

## 🛡 Defensive Insight

AI systems should never be relied upon as the sole mechanism for protecting sensitive information.

Language models are designed to generate text rather than enforce strict security policies.

To secure AI systems, organizations should:

- enforce server-side authorization checks  
- avoid storing secrets within model-accessible prompts  
- implement output filtering mechanisms  
- monitor for prompt injection attempts  

AI interfaces should be treated as **untrusted input surfaces**, similar to traditional web forms.

---

## 💡 Skills Reinforced

- AI system security testing  
- Prompt injection techniques  
- Language model behavior analysis  
- Security evaluation of conversational interfaces  
- Understanding emerging AI attack surfaces  

---

<div align="center">

🧠 AI systems can be manipulated through language  
🔍 Prompt injection bypasses model safeguards  
🔐 Security controls must exist outside the AI  

</div>
