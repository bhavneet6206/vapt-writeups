# Sensitive Data Exposure via Insecure JWT Implementation

> Successfully identified sensitive information disclosure through improperly designed JWT tokens, exposing administrative credentials and internal user data.

---

## 🧠 Objective
Analyze authentication tokens to identify potential security misconfigurations leading to sensitive data exposure.

---

## 🛠️ Environment
- Platform: OWASP Juice Shop  
- Vulnerability Type: Sensitive Data Exposure / Broken Authentication  
- Tool Used: Browser DevTools, JWT.io  

---

## 🔍 Vulnerability Description

The application stores a JSON Web Token (JWT) in the browser's Local Storage after authentication. Upon decoding the token, sensitive user information is exposed, including:

- User email  
- User role (admin)  
- Password hash  
- Account metadata  

This indicates improper handling of JWT payloads, where confidential data is embedded directly into the token without encryption.

---

## 💥 Proof of Concept (PoC)

<img width="1905" height="963" alt="Screenshot 2026-03-25 141812" src="https://github.com/user-attachments/assets/a0c78f2e-7dbe-4a92-96c3-08f3968b1244" />
<img width="1183" height="805" alt="Screenshot 2026-03-25 142051" src="https://github.com/user-attachments/assets/6282ee47-22ab-4958-a55e-2030bb3aa492" />


### Step 1: Access Local Storage
- Open browser DevTools (F12)  
- Navigate to:  
  `Application → Local Storage → https://demo.owasp-juice.shop`  

### Step 2: Extract JWT Token
- Locate the `token` key  
- Copy the JWT value  

---

### Step 3: Decode Token
- Navigate to https://jwt.io  
- Paste the token  

---

### Step 4: Analyze Payload

```json
{
  "status": "success",
  "data": {
    "id": 1,
    "email": "admin@juice-sh.op",
    "password": "0192023a7bbd73250516f069df18b500",
    "role": "admin",
    "isActive": true
  }
}
