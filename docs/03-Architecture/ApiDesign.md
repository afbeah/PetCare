# API Design

## Objetivo

Este documento define os princípios, padrões e convenções da API REST da plataforma PetCare.

Seu objetivo é garantir consistência entre todos os endpoints, facilitar a integração entre frontend e backend e servir como referência para implementação e documentação da API.

A API deverá seguir os princípios RESTful, utilizando recursos bem definidos, operações padronizadas e respostas previsíveis.

---

# Objetivos

A API deverá ser:

- consistente;
- previsível;
- versionável;
- segura;
- escalável;
- fácil de consumir.

---

# Arquitetura

A comunicação entre clientes e servidores será realizada através de HTTP utilizando JSON como formato padrão de troca de dados.

```text
Frontend

↓

REST API

↓

Application Layer

↓

Domain Layer

↓

Persistence Layer
```

---

# Base URL

A API deverá utilizar versionamento por URI.

Exemplo:

/api/v1

Futuras versões poderão coexistir:

/api/v2

---

# Recursos

Os recursos representam entidades do domínio.

Principais recursos:

- Users
- Pets
- Vaccines
- Appointments
- Medications
- Allergies
- Events
- Authentication

---

# Convenções de Rotas

Os nomes dos recursos deverão utilizar substantivos no plural.

Exemplos:

GET /pets

GET /pets/{id}

POST /pets

PUT /pets/{id}

PATCH /pets/{id}

DELETE /pets/{id}

---

# Métodos HTTP

GET

Consulta informações.

POST

Cria recursos.

PUT

Atualiza completamente.

PATCH

Atualiza parcialmente.

DELETE

Remove recursos.

---

# Estrutura das URLs

As URLs deverão representar recursos.

Correto:

/pets

/pets/{id}

/pets/{id}/vaccines

/pets/{id}/appointments

Evitar verbos na URL.

Incorreto:

/createPet

/getVaccines

/updateAppointment

---

# Formato de Requisições

Todas as requisições utilizarão JSON.

Exemplo:

{
  "name": "Luna",
  "species": "Dog",
  "breed": "Golden Retriever",
  "birthDate": "2024-01-15"
}

---

# Formato das Respostas

Resposta de sucesso:

{
  "data": { ... }
}

Resposta de coleção:

{
  "data": [ ... ]
}

---

# Paginação

Listagens deverão suportar paginação.

Parâmetros:

?page=1

&limit=20

Resposta:

{
  "data": [],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 58,
    "pages": 3
  }
}

---

# Ordenação

A API deverá permitir ordenação.

Exemplo:

?sort=name

?sort=-createdAt

---

# Filtros

Filtros deverão utilizar Query Parameters.

Exemplo:

?species=dog

?status=active

?name=luna

---

# Busca

Busca textual deverá utilizar:

?q=luna

---

# Versionamento

A API deverá ser versionada.

Exemplo:

/api/v1

Novas versões não deverão quebrar clientes existentes.

---

# Autenticação

A autenticação utilizará JWT.

Cabeçalho:

Authorization

Bearer <token>

---

# Códigos HTTP

200 OK

Consulta realizada.

201 Created

Recurso criado.

204 No Content

Exclusão realizada.

400 Bad Request

Erro de validação.

401 Unauthorized

Usuário não autenticado.

403 Forbidden

Acesso negado.

404 Not Found

Recurso inexistente.

409 Conflict

Conflito de negócio.

422 Unprocessable Entity

Erro de validação de domínio.

500 Internal Server Error

Erro inesperado.

---

# Estrutura de Erros

Todas as respostas de erro deverão seguir o mesmo formato.

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

---

# Datas

Datas deverão utilizar ISO-8601.

Exemplo:

2026-07-20T18:30:00Z

---

# Identificadores

Todos os recursos deverão possuir identificadores únicos.

Formato recomendado:

UUID

---

# Segurança

A API deverá:

- validar autenticação;
- validar autorização;
- sanitizar entradas;
- proteger contra ataques comuns;
- registrar operações críticas.

---

# Idempotência

Operações PUT e DELETE deverão ser idempotentes.

---

# Upload de Arquivos

Uploads deverão utilizar multipart/form-data.

Exemplos:

- foto do pet;
- documentos;
- exames.

---

# Documentação

A API deverá possuir documentação OpenAPI (Swagger).

A documentação deverá incluir:

- endpoints;
- parâmetros;
- exemplos;
- códigos de resposta;
- schemas.

---

# Boas Práticas

- URLs intuitivas;
- respostas consistentes;
- mensagens claras;
- baixo acoplamento;
- versionamento;
- contratos estáveis.

---

# Relação com outros documentos

Este documento complementa:

- BackendArchitecture.md
- DatabaseDesign.md
- SecurityArchitecture.md
- TechnologyStack.md
