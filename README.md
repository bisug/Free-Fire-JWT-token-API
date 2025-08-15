# 🔑 Free Fire JWT API

A simple API to generate JWT tokens for Free Fire accounts using UID and password.

> ⚠ **Disclaimer**:  
> This API is for educational and integration purposes only.  

## 🌐 Base URL
```
https://sumi-jwt-01.vercel.app 
```
```
https://sumi-jwt-02.vercel.app 
```
```
https://sumi-jwt-03.vercel.app 
```
```
https://sumi-jwt-04.vercel.app 
```
```
https://sumi-jwt-05.vercel.app 
```
```
https://sumi-jwt-06.vercel.app 
```
```
https://sumi-jwt-07.vercel.app 
```
```
https://sumi-jwt-08.vercel.app 
```
```
https://sumi-jwt-09.vercel.app 
```
```
https://sumi-jwt-10.vercel.app 
```

---

## 📌 Endpoint
```
GET /token?uid={uid}&password={password}
```

### Query Parameters
| Parameter | Type   | Required | Description |
|-----------|--------|----------|-------------|
| `uid`     | string | ✅ Yes   | Free Fire account UID |
| `password`| string | ✅ Yes   | Free Fire account password (hashed) |

---

## 📦 Example Request
```http
GET https://ff-jwt-api-lake.vercel.app/token?uid=3562381559&password=AF18F2EB5A410D815F54B16EAEAC369FC027E96925005A629E90A823996B0240
```

---

## ✅ Success Response
```json
{
  "status": "live",
  "token": "eyJhbGciOiJIUzI1NiIsInN2ciI6IjMiLCJ0eXAiOiJKV1QifQ....",
  "uid": "12345678910"
}
```

---

## ❌ Error Responses
| HTTP Code | Example Response | Reason |
|-----------|------------------|--------|
| 400 | `{"error": "Both uid and password parameters are required"}` | Missing parameters |
| 400 | `{"status": "invalid", "message": "Wrong UID or Password"}` | Invalid credentials |
| 400 | `{"error": "Failed to get response: HTTP 500"}` | Upstream server error |
| 500 | `{"error": "Internal error occurred"}` | Internal API error |

---

## 📝 Notes
- Tokens expire at the `exp` timestamp inside the JWT.
- Responses are cached for 7 hours to reduce API calls.
- Uses the official Free Fire backend for token retrieval.
- SSL certificate warnings are bypassed internally for compatibility.

---
