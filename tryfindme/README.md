<div align="center">

# 🔎 TryFindMe  
## OSINT Geolocation & Reverse Image Investigation

![Category](https://img.shields.io/badge/Category-OSINT-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Geolocation-blue?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-Reverse%20Image%20Search-success?style=for-the-badge)

</div>

---

### 🎯 Objective

Investigate an image to determine where the photograph was taken.

The challenge required analyzing the provided image and using **open-source intelligence (OSINT) techniques** to identify the location where the photo originated.

The objective was to perform **geolocation analysis** using publicly available information.

---

### 🖥 Environment

| Tool | Purpose |
|-----|------|
| Kali Linux AttackBox | Investigation environment |
| `wget` | Download the provided image |
| Web browser | OSINT research |
| Reverse image search | Identify image origin |

---

### 📦 Step 1 — Retrieve the Image

The investigation began by downloading the image provided in the challenge.

```bash
wget http://10.10.31.145/surfsup.jpg
```

The downloaded file appeared to show a well-known surfing location.

Because the challenge asked for the location of the photograph, the next step was to perform **reverse image analysis**.

---

### 🔍 Step 2 — Perform Reverse Image Search

To identify the location of the image, a reverse image search was performed.

Reverse image searches allow investigators to locate where images appear online and identify related sources.

One of the search results referenced a surfing event article containing the same image.

📸 **Reverse Image Search Result**

<img src="../images/image046.5.png" width="600">

The article referenced the location **Jeffreys Bay**, a famous surfing destination.

---

#### 🔎 Analytical Observation

Reverse image searches are a powerful OSINT technique used to:

- identify image origins  
- locate duplicate images online  
- discover contextual information about a photograph  

This technique is commonly used in investigations involving:

- geolocation analysis  
- misinformation detection  
- digital investigations  

---

### 🔄 Step 3 — Verify the Location

Additional research confirmed that the image corresponded to **Jeffreys Bay**, a well-known surfing location in South Africa.

Jeffreys Bay is internationally recognized for its surf breaks, particularly **Supertubes**, which is considered one of the most famous right-hand point breaks in the world.

Comparing images of the location with the challenge image confirmed the match.

---

### 🔐 Step 4 — Confirm the Investigation Result

After verifying the location of the photograph, the answer was formatted according to the challenge requirements.

```
THM{[redacted]}
```

This confirmed that the image was taken at **Jeffreys Bay**.

---

## 🧠 Methodology Framework Applied

```
Image obtained
      ↓
Reverse image search performed
      ↓
Matching locations identified
      ↓
Location verified through OSINT
      ↓
Correct location confirmed
```

---

## 🛠 Techniques Used

Primary techniques used:

- reverse image search  
- OSINT investigation  
- geolocation analysis  
- public information verification  

Key concept investigated:

```
Image geolocation
```

---

## 🛡 Defensive Insight

Images shared online can unintentionally reveal sensitive location information.

Metadata, recognizable landmarks, and publicly indexed images can allow investigators to determine where photographs were taken.

Organizations and individuals should consider:

- removing metadata from images before publishing  
- avoiding sharing sensitive locations publicly  
- reviewing images for identifiable landmarks  

These precautions help reduce the risk of unintended location disclosure.

---

## 💡 Skills Reinforced

- OSINT investigation  
- Reverse image search techniques  
- Image geolocation analysis  
- Public information correlation  

---

<div align="center">

🔎 Images often reveal more than expected  
🌍 Reverse image search helps identify locations  
🧠 OSINT connects digital clues to real-world places  

</div>
