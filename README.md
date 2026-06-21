# 🇵🇰 Benefits Navigator Pakistan

> An AI-powered chatbot that helps people in Pakistan understand which public support programs they may qualify for — and guides them on exactly what to do next.

Built for **USAII Global AI Hackathon 2026** | Challenge 4 — Fix Systems People Depend On | Undergraduate Track

---

## 🎯 What It Does

Millions of Pakistanis are eligible for government support programs — BISP, Ehsaas Kafalat, Sehat Sahulat, scholarships, skills training — but never access them because the system is confusing, fragmented, and hard to navigate.

**Benefits Navigator Pakistan** solves this by letting a user describe their situation in plain language. The AI then:
- Asks focused follow-up questions (province, household size, income, CNIC status)
- Reasons through eligibility criteria in plain language
- Names specific programs they **may** qualify for and explains why
- Gives concrete next steps — which office to visit, which helpline to call, which documents to bring
- Supports both **English and Urdu**

---

## 🖥️ Live Demo

🔗 **[https://rahnuma-production.up.railway.app/](https://rahnuma-production.up.railway.app/)**

---

## 🎬 Demo Video

🎥 **[[Add your demo video link here — YouTube / Google Drive / Loom]]**

> [[Add a 1-line description of what the video covers — e.g. "A user describes their situation in Urdu and receives tailored program recommendations in under 60 seconds."]]

---

## 💥 Decision Impact

Before Rahnuma, a low-income family in Pakistan had to:
- Know which programs exist (most don't)
- Visit multiple government offices to ask about eligibility
- Understand complex bureaucratic criteria in formal language
- Gather documents without knowing if they'd even qualify

**With Rahnuma, this changes:**
- A widow in rural Punjab can describe her situation in Urdu and learn about BISP and Sehat Sahulat in under 2 minutes — from her phone, without visiting any office
- A daily wage worker finds out exactly which documents to bring before making a trip to the BISP Tehsil Office, saving a wasted journey
- A university student from a low-income family discovers the Ehsaas Undergraduate Scholarship — full tuition covered — that they never knew existed

The result: **eligible people actually access the support they are entitled to**, instead of missing out because the system was too hard to navigate.

---

## 🏗️ How It Works

```
User Input (English or Urdu)
        ↓
Flask Backend (server.py)
        ↓
Llama 3.3 70B via Groq API
  - System prompt encodes all Pakistani benefit program rules
  - Reasons through eligibility step by step
  - Asks follow-up questions progressively
        ↓
Structured Response
  - Programs you may qualify for
  - Why each applies
  - Documents needed
  - Next steps
  - Human referral (agency / helpline)
        ↓
User sees actionable guidance in the chat UI
```

### AI Capabilities Used
| Capability | How it's used |
|---|---|
| Conversational AI | Guided intake with follow-up questions |
| Natural Language Understanding | Parses user's free-text situation |
| Eligibility Reasoning | Maps user details to program criteria |
| Recommendation | Surfaces relevant programs and next steps |

---

## 🇵🇰 Programs Covered

| Category | Programs |
|---|---|
| Income Support | BISP, Ehsaas Kafalat, Zakat |
| Food Assistance | Ehsaas Ration Riayat, Punjab Ration Card, USC Subsidy |
| Healthcare | Sehat Sahulat Programme, Sehat Card Plus (Punjab), Ehsaas Nashonuma |
| Education | Ehsaas Undergraduate Scholarship, PEEF, Ehsaas Wazaif |
| Employment & Skills | Kamyab Jawan, NAVTTC, Hunarmand Pakistan, Punjab Rozgar Scheme |
| Housing | Naya Pakistan Housing Programme, Ehsaas Langar |
| Emergency / Disaster | PDMA Relief, Ehsaas Emergency Cash, NDRMF |
| Persons with Disability | STEP Programme, BISP priority group, Disability certificates |

---

## 🛡️ Responsible AI

This project takes responsible AI seriously — not as a checkbox, but as a design principle.

| Safeguard | Implementation |
|---|---|
| **"May qualify" framing only** | The AI never says "you qualify." Every eligibility statement uses hedged language: "you may qualify", "aap eligible ho sakte hain." Enforced in the system prompt. |
| **Human in the loop** | The AI never makes official decisions. Every response ends with a named agency, helpline, or office the user must contact for verification. |
| **Source transparency** | The AI explains which criteria it is reasoning from, so users and caseworkers can verify independently. |
| **Persistent disclaimer** | A visible disclaimer bar is always shown: "This tool helps you explore — it does not make official eligibility decisions." |

### Risk & Mitigation
- **Risk:** Over-reliance — user treats AI output as a guaranteed eligibility decision
- **Mitigation:** Hedged language + mandatory human referral + persistent disclaimer on every page

### Human-in-the-Loop Decision
The AI **never** makes a final eligibility determination. A human caseworker or official government body always has final authority — because eligibility requires document verification, real-time rule checking, and case-by-case discretion that no AI can reliably provide.

---

## 🚀 Running Locally

### Prerequisites
- Python 3.8+
- A Groq API key from [console.groq.com](https://console.groq.com/)

### Setup

**1. Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/benefits-navigator.git
cd benefits-navigator
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Add your Groq API key**

Open `server.py` and replace line 11:
```python
API_KEY = "your_groq_api_key_here"
```

**4. Run the server**
```bash
python server.py
```

**5. Open in browser**
```
http://localhost:5000
```

---

## 📁 Project Structure

```
benefits-navigator/
├── server.py          # Flask backend — Groq API integration
├── login.py           # User authentication (register / login / session)
├── index.html         # Frontend chatbot UI
├── requirements.txt   # Python dependencies (flask, groq, gunicorn)
├── favicon.ico        # App favicon
├── favicon.png        # App favicon (PNG)
├── apple-touch-icon.png  # iOS home screen icon
├── AI_Architecture.png   # Architecture diagram
└── README.md          # This file
```

---

## 🧰 Tech Stack

| Layer | Technology |
|---|---|
| AI Model | Llama 3.3 70B (via Groq) |
| Backend | Python, Flask, Flask-CORS |
| Frontend | HTML, CSS, JavaScript (vanilla) |
| Auth | SQLite-based login system (login.py) |
| Deployment | Railway |
| Icons | Tabler Icons |

---

## 👥 Who It's Built For

- Families in Pakistan who don't know what support they're eligible for
- Widows, daily wage workers, students, persons with disability
- Community case managers helping vulnerable individuals
- Anyone navigating the Pakistani social support system under stress

---

## ⚠️ Disclaimer

This tool provides **exploratory guidance only**. It is not an official government service and does not make binding eligibility determinations. Always verify with the relevant government office, helpline, or caseworker.

---

## 📬 Contact & Submission

- **Hackathon:** USAII Global AI Hackathon 2026
- **Track:** Undergraduate
- **Challenge:** 4 — Fix Systems People Depend On
- **Direction:** A — Benefits Navigator
