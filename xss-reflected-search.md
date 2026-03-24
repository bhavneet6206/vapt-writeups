> Successfully exploited a reflected Cross-Site Scripting (XSS) vulnerability to execute arbitrary JavaScript in the victim’s browser.

## 🔍 Vulnerability Description
The application reflects user input directly into the HTML response without proper sanitization or encoding. This allows attackers to inject and execute malicious JavaScript in the victim’s browser.

## 💥 Payload Variations Tested
```html
<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
<svg onload=alert('XSS')>

**## 🔹 4. Upgrade Impact Section**
```md
## ⚠️ Impact
- Execution of arbitrary JavaScript in user browsers  
- Session hijacking via cookie theft  
- Credential harvesting through malicious scripts  
- Redirection to phishing or malicious websites  
- Potential account takeover

## 🌍 Real-World Scenario
An attacker could craft a malicious link containing the XSS payload and trick users into clicking it. When opened, the script executes in the user’s browser, potentially stealing session cookies or redirecting them to a phishing page.

## 📸 Proof of Exploit

<img width="1643" height="647" alt="Screenshot 2026-03-24 143436" src="https://github.com/user-attachments/assets/e8f518f6-01f5-400d-9221-77ccae9fac6d" />
