# JobKing API Spec (Draft)

<!---
@application    : JobKing-API
@author         : Gafrilatif Aviandi Putra Adnanta
@contributor  : 
      1. Rafaiz Ghazian Lusaid <insert the date>
         <insert what you have modified>         
      2. <insert your fullname> (<insert your nik>) <insert the date>
         <insert what you have modified>
      etc.
-->

## 1. Auth

### POST /api/login
Request (JSON):
{
    "email": "yuyus@gmail.com",
    "password": "anjing12"
}

Response 200:
{
    "token": "JA_STRING",
    "user": {
        "id": 1,
        "name": "Yuyus",
        "role": "Candidate" // or "employer", "admin"
    }
}

Response 401:
{
    "message": "Salah bro"
}

---

## 2. Jobs

### GET/api/jobs
Query params:
- 'search' (optional)
- 'page' (optional, default 1)
- 'limit' (optional, default 10)

Response 200:
{
    "data": [
    {
      "id": 1,
      "title": "Frontend Developer",
      "company": "Jobking Inc",
      "location": "Remote",
      "salary_min": 8000000,
      "salary_max": 12000000,
      "created_at": "2025-12-01T10:00:00Z"
    }
  ],
  "page": 1,
  "total": 35
}

### GET /api/jobs/:id
Response 200:
{
  "id": 1,
  "title": "Frontend Developer",
  "company": "Jobking Inc",
  "location": "Remote",
  "description": "Full job description...",
  "requirements": ["React", "JS", "Git"],
  "salary_min": 8000000,
  "salary_max": 12000000,
  "created_at": "2025-12-01T10:00:00Z"
}

