# 🕵️ Ethical OSINT Investigation - Company X

This repository documents a **legal and ethical** Open Source Intelligence (OSINT) exercise I performed for educational purposes. The goal was to identify publicly exposed information related to a real company’s web infrastructure, without accessing or interfering with private systems.

---

## ⚠️ Disclaimer

> This investigation was conducted **strictly within legal boundaries**:
> - Only publicly accessible data was analyzed.
> - No authentication bypasses or unauthorized access attempts were made.
> - No vulnerabilities were exploited.
> - The purpose was **educational and non-malicious**.

---

## 🎯 Target Scope

- Domain format: `*.example.com`
- Only subdomains and publicly available directories/services were targeted.
- Tools used simulated what any search engine or OSINT tool could legally access.

---

## 🧰 Tools Used

- amass — subdomain enumeration  
- curl — HTTP header analysis  
- gobuster — directory discovery  
- whois 
 - Tor — anonymous browsing  

---

## 🔎 Key Findings

- Multiple subdomains identified via amass, including some pointing to staging environments.
- Existence of directories such as /debug, /checkout, /plugins, /includes, and others.
- HTTP response headers revealed:
  - Server technology stack (e.g. Apache, PHP 7.3, IIS)
  - Cookies with potential session tokens
-/debug endpoint revealed an **internal IP address** used for outbound requests.
- /checkout appeared to link to a **live payment processing interface**.

---

## 💡 Observations

- Some directories returned HTTP 200 or 301 responses, suggesting potential exposure of unused or sensitive areas.
- The /debug endpoint **should not be exposed** in production environments.
- No login bypasses, code injections, or vulnerability scans were performed.

---

## 📚 What I Learned

- How to enumerate subdomains and directories in a controlled and legal manner.
- How to interpret HTTP headers and cookie metadata.
- Importance of obscuring or securing non-public endpoints like /debug.
- Ethical boundaries in recon work and how to stay compliant.

---


## 📎 Notes

This was my first real world OSINT reconnaissance and I learned a lot about passive footprinting, responsible disclosure mindset, and the importance of respecting legal boundaries while training offensive security skills.
