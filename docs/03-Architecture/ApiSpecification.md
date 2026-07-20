# API Specification

## Objetivo

Este documento especifica os endpoints da API REST da plataforma PetCare.

Seu objetivo é definir o contrato entre frontend e backend, documentando recursos, rotas, parâmetros, payloads, respostas e códigos HTTP esperados.

A especificação segue os padrões definidos em `ApiDesign.md`.

---

# Informações Gerais

## Base URL

```text
/api/v1
```

## Formato

Todas as requisições e respostas utilizam:

```text
application/json
```

## Autenticação

Endpoints protegidos exigem:

```http
Authorization: Bearer <JWT_TOKEN>
```

---

# Authentication

## Login

### Endpoint

```http
POST /auth/login
```

### Request

```json
{
  "email": "user@email.com",
  "password": "123456"
}
```

### Response

```json
{
  "data": {
    "token": "...",
    "expiresIn": 3600,
    "user": {
      "id": "...",
      "name": "Beatriz França",
      "email": "user@email.com"
    }
  }
}
```

### Status

- 200 OK
- 400 Bad Request
- 401 Unauthorized

---

## Register

### Endpoint

```http
POST /auth/register
```

### Request

```json
{
  "name": "Beatriz França",
  "email": "user@email.com",
  "password": "123456"
}
```

### Response

```json
{
  "data": {
    "id": "uuid"
  }
}
```

### Status

- 201 Created
- 400 Bad Request
- 409 Conflict

---

# Users

## Get Profile

```http
GET /users/me
```

### Response

```json
{
  "data": {
    "id": "...",
    "name": "...",
    "email": "..."
  }
}
```

---

## Update Profile

```http
PUT /users/me
```

### Request

```json
{
  "name": "Novo Nome"
}
```

### Status

- 200 OK
- 400 Bad Request

---

# Pets

## List Pets

```http
GET /pets
```

### Query Parameters

```text
?page=1

&limit=20

&sort=name
```

### Response

```json
{
  "data": [
    {
      "id": "...",
      "name": "Luna",
      "species": "Dog"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 1,
    "pages": 1
  }
}
```

---

## Get Pet

```http
GET /pets/{id}
```

---

## Create Pet

```http
POST /pets
```

### Request

```json
{
  "name": "Luna",
  "species": "Dog",
  "breed": "Golden Retriever",
  "sex": "Female",
  "birthDate": "2024-01-15"
}
```

### Response

```json
{
  "data": {
    "id": "uuid"
  }
}
```

### Status

- 201 Created
- 400 Bad Request

---

## Update Pet

```http
PUT /pets/{id}
```

---

## Delete Pet

```http
DELETE /pets/{id}
```

### Status

- 204 No Content

---

# Vaccines

## List Vaccines

```http
GET /pets/{petId}/vaccines
```

---

## Register Vaccine

```http
POST /pets/{petId}/vaccines
```

### Request

```json
{
  "name": "V10",
  "applicationDate": "2026-07-20",
  "nextDose": "2027-07-20",
  "veterinarian": "Dr. João"
}
```

---

## Update Vaccine

```http
PUT /vaccines/{id}
```

---

## Delete Vaccine

```http
DELETE /vaccines/{id}
```

---

# Appointments

## List Appointments

```http
GET /pets/{petId}/appointments
```

---

## Register Appointment

```http
POST /pets/{petId}/appointments
```

### Request

```json
{
  "date": "2026-08-10T14:00:00Z",
  "clinic": "PetCare Clinic",
  "veterinarian": "Dr. João",
  "diagnosis": "Check-up"
}
```

---

## Update Appointment

```http
PUT /appointments/{id}
```

---

## Delete Appointment

```http
DELETE /appointments/{id}
```

---

# Medications

## List Medications

```http
GET /pets/{petId}/medications
```

---

## Register Medication

```http
POST /pets/{petId}/medications
```

### Request

```json
{
  "name": "Antibiótico",
  "dosage": "10mg",
  "frequency": "2x ao dia",
  "startDate": "2026-07-20",
  "endDate": "2026-07-30"
}
```

---

## Update Medication

```http
PUT /medications/{id}
```

---

## Delete Medication

```http
DELETE /medications/{id}
```

---

# Allergies

## List Allergies

```http
GET /pets/{petId}/allergies
```

---

## Register Allergy

```http
POST /pets/{petId}/allergies
```

### Request

```json
{
  "name": "Frango",
  "severity": "High",
  "description": "Reação alérgica alimentar"
}
```

---

## Update Allergy

```http
PUT /allergies/{id}
```

---

## Delete Allergy

```http
DELETE /allergies/{id}
```

---

# Events

## List Events

```http
GET /pets/{petId}/events
```

---

## Create Event

```http
POST /pets/{petId}/events
```

### Request

```json
{
  "title": "Banho",
  "description": "Banho mensal",
  "date": "2026-07-25T09:00:00Z",
  "type": "Reminder"
}
```

---

## Update Event

```http
PUT /events/{id}
```

---

## Delete Event

```http
DELETE /events/{id}
```

---

# Uploads

## Upload Pet Photo

```http
POST /pets/{id}/photo
```

### Content-Type

```text
multipart/form-data
```

### Response

```json
{
  "data": {
    "url": "https://..."
  }
}
```

---

# Error Response

Todos os erros seguem o padrão:

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Validation failed.",
    "details": [
      {
        "field": "email",
        "message": "Invalid email."
      }
    ]
  }
}
```

---

# HTTP Status Codes

| Código | Descrição |
|---------|-----------|
| 200 | OK |
| 201 | Created |
| 204 | No Content |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 409 | Conflict |
| 422 | Unprocessable Entity |
| 500 | Internal Server Error |

---

# Versionamento

A API utiliza versionamento por URI.

Exemplo:

```text
/api/v1
```

Mudanças incompatíveis deverão originar uma nova versão da API.

---

# Relação com outros documentos

Este documento complementa:

- ApiDesign.md
- BackendArchitecture.md
- SecurityArchitecture.md
- DatabaseDesign.md
