<div align="center">

# 📝 Notepad Online  
## Authorization Logic Analysis & Direct Object Reference Investigation

![Category](https://img.shields.io/badge/Category-Web%20Security-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Authorization%20Control-blue?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-Parameter%20Manipulation-success?style=for-the-badge)

</div>

---

### 🎯 Objective

Investigate a web-based note-taking application that claims user notes are **only visible to the account owner**.

The challenge involved authenticating to the application and analyzing how the system retrieves stored notes.

The objective was to determine whether the application properly enforced **authorization controls** or whether user data could be accessed by manipulating request parameters.

---

### 🖥 Environment

| Tool | Purpose |
|-----|------|
| Web browser | Interact with the target application |
| Browser address bar | Modify request parameters |
| Manual testing | Authorization validation |

---

### 📦 Step 1 — Authenticate to the Application

The investigation began by logging into the application using the credentials provided by the challenge.

```
User: noel
Pass: pass1234
```

After authenticating successfully, the application displayed the user’s notes.

At first glance, the application appeared to restrict access to the authenticated user's content.

---

### 🔍 Step 2 — Inspect Application Behavior

After logging in, the browser address bar revealed that the application retrieved notes using an **ID parameter**.

Example URL:

```
?id=1
```

Applications that use predictable identifiers can sometimes expose data belonging to other users if authorization checks are not properly enforced.

This type of vulnerability is commonly known as an **Insecure Direct Object Reference (IDOR)**.

---

### 🧪 Step 3 — Manipulate the Identifier Parameter

To test whether the application validated note ownership, the ID parameter was manually modified.

Original request:

```
?id=1
```

Modified request:

```
?id=0
```

If authorization controls were properly implemented, the application should reject this request or return an error.

---

### 🔐 Step 4 — Confirm Unauthorized Data Access

After modifying the ID parameter, the application returned data belonging to another user.

📸 **Unauthorized Note Access**

<img src="../images/image008_redacted.png" width="600">

This confirmed that the application did not verify whether the authenticated user was authorized to access the requested note.

---

## 🧠 Methodology Framework Applied

```
Application accessed
      ↓
Authentication performed
      ↓
Request parameters inspected
      ↓
Identifier modified
      ↓
Unauthorized data accessed
```

---

## 🛠 Techniques Used

Primary techniques used:

- web application testing  
- parameter manipulation  
- authorization control testing  

Key concept investigated:

```
Insecure Direct Object Reference (IDOR)
```

---

## 🛡 Defensive Insight

Applications must enforce proper **authorization checks** when retrieving user data.

Even when users are authenticated, the system must verify that they are authorized to access the requested resource.

Secure implementations should:

- validate resource ownership
- avoid predictable identifiers
- enforce server-side authorization checks

Failure to implement these controls can allow attackers to access other users’ data.

---

## 💡 Skills Reinforced

- Web application reconnaissance  
- Authorization testing  
- Parameter manipulation  
- Identifying IDOR vulnerabilities  

---

<div align="center">

📝 Authentication does not equal authorization  
🔍 Always test parameter-based access controls  
🧠 IDOR vulnerabilities can expose sensitive data  

</div>
