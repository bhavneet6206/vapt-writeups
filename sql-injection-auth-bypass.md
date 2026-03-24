> Successfully exploited SQL Injection vulnerability to bypass authentication and gain unauthorized access to user accounts.

# 🔓 SQL Injection Attack – Authentication Bypass & Data Extraction

---

## 📌 Target Details

* **Application:** OWASP Juice Shop
* **Vulnerability:** SQL Injection
* **Type:** Authentication Bypass

---

## ⚙️ Tools Used

* Burp Suite
* Web Browser

---

## 🚨 Vulnerability Description

SQL Injection is a critical vulnerability that allows attackers to manipulate backend database queries by injecting malicious SQL code into input fields. This can lead to unauthorized access, data leakage, and full system compromise.

---

## 💥 Exploitation Steps

### 🔹 Step 1: Identify Input Field

The login page was tested for injection vulnerabilities in the email input field.

---

### 🔹 Step 2: Test SQL Injection Payload

Payload used:

```
' OR 1=1--
```

---

### 🔹 Step 3: Authentication Bypass

* Entered payload in the email field
* Used random password
* Successfully logged in without valid credentials

---

## 📸 Proof of Concept

### 🧪 Payload Injection

<img width="1875" height="877" alt="Screenshot 2026-03-24 111639" src="https://github.com/user-attachments/assets/084789c7-00dd-4e7e-a819-03e0f64e07d8" />


### ✅ Successful Login

<img width="1885" height="733" alt="Screenshot 2026-03-24 111836" src="https://github.com/user-attachments/assets/a88bacea-0bb1-4135-bf01-ae31b5c91f57" />

---

## ⚠️ Impact

* Unauthorized access to user accounts
* Authentication bypass
* Potential exposure of sensitive user data
* Risk of full database compromise

---

## 🛡️ Mitigation

* Use parameterized queries / prepared statements
* Implement strict input validation
* Apply least privilege principle for database access
* Use Web Application Firewalls (WAF)

---

## 🧠 Key Learnings

* SQL Injection remains one of the most critical web vulnerabilities
* Improper input validation can lead to severe security breaches
* Even basic payloads can bypass authentication mechanisms

---
