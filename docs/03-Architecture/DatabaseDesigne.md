# Database Design

## Objetivo

Este documento descreve o projeto físico do banco de dados da plataforma PetCare.

Seu objetivo é definir como as informações do domínio serão persistidas, organizadas e consultadas, garantindo desempenho, consistência e escalabilidade.

A implementação utiliza MongoDB como banco de dados NoSQL orientado a documentos.

---

# Objetivos

A camada de persistência deverá:

- armazenar dados de forma consistente;
- suportar crescimento da aplicação;
- otimizar consultas frequentes;
- minimizar duplicação desnecessária;
- facilitar manutenção e evolução.

---

# Tecnologia

Banco de Dados

- MongoDB

Características utilizadas:

- Document Database
- BSON
- Índices
- Agregações
- TTL Index (quando aplicável)

---

# Estratégia de Modelagem

O modelo utiliza uma abordagem híbrida, combinando:

- Referencing
- Embedding

Cada decisão considera:

- frequência de leitura;
- frequência de escrita;
- tamanho esperado dos documentos;
- facilidade de manutenção.

---

# Collections

A aplicação é composta pelas seguintes collections:

- users
- pets
- vaccines
- appointments
- medications
- allergies
- events

---

# Collection: users

Representa os usuários da plataforma.

## Estrutura

```json
{
  "_id": "uuid",
  "name": "Beatriz França",
  "email": "beatriz@email.com",
  "passwordHash": "...",
  "createdAt": "...",
  "updatedAt": "..."
}
```

## Índices

```text
_id

email (unique)
```

---

# Collection: pets

Representa os animais cadastrados.

## Estrutura

```json
{
  "_id": "uuid",
  "ownerId": "uuid",
  "name": "Luna",
  "species": "Dog",
  "breed": "Golden Retriever",
  "sex": "Female",
  "birthDate": "2024-01-15",
  "weight": 18.5,
  "photo": "...",
  "notes": "...",
  "createdAt": "...",
  "updatedAt": "..."
}
```

## Índices

```text
_id

ownerId

name

species
```

---

# Collection: vaccines

## Estrutura

```json
{
  "_id": "uuid",
  "petId": "uuid",
  "name": "V10",
  "applicationDate": "...",
  "nextDose": "...",
  "veterinarian": "...",
  "notes": "...",
  "createdAt": "...",
  "updatedAt": "..."
}
```

## Índices

```text
petId

applicationDate

nextDose
```

---

# Collection: appointments

```json
{
  "_id": "uuid",
  "petId": "uuid",
  "date": "...",
  "clinic": "...",
  "veterinarian": "...",
  "diagnosis": "...",
  "notes": "...",
  "createdAt": "...",
  "updatedAt": "..."
}
```

## Índices

```text
petId

date
```

---

# Collection: medications

```json
{
  "_id": "uuid",
  "petId": "uuid",
  "name": "...",
  "dosage": "...",
  "frequency": "...",
  "startDate": "...",
  "endDate": "...",
  "observations": "...",
  "createdAt": "...",
  "updatedAt": "..."
}
```

## Índices

```text
petId

startDate

endDate
```

---

# Collection: allergies

```json
{
  "_id": "uuid",
  "petId": "uuid",
  "name": "...",
  "severity": "High",
  "description": "...",
  "createdAt": "...",
  "updatedAt": "..."
}
```

## Índices

```text
petId

severity
```

---

# Collection: events

```json
{
  "_id": "uuid",
  "petId": "uuid",
  "title": "...",
  "description": "...",
  "date": "...",
  "type": "Vaccination",
  "completed": false,
  "createdAt": "...",
  "updatedAt": "..."
}
```

## Índices

```text
petId

date

completed
```

---

# Relacionamentos

A aplicação utiliza relacionamento por referência.

```text
User

│

└── ownerId

↓

Pet

│

└── petId

↓

Vaccine

↓

Appointment

↓

Medication

↓

Allergy

↓

Event
```

---

# Estratégia de Referências

Será utilizada referência entre collections para:

- evitar documentos excessivamente grandes;
- facilitar consultas independentes;
- permitir evolução das entidades.

Exemplo:

```json
{
  "petId": "uuid"
}
```

---

# Estratégia de Embedding

Objetos pequenos e fortemente relacionados poderão ser incorporados ao documento principal.

Exemplos:

- configurações do usuário;
- preferências;
- informações simples sem necessidade de consultas independentes.

---

# Auditoria

Sempre que aplicável, os documentos possuirão:

```text
createdAt

updatedAt
```

Futuras versões poderão incluir:

```text
createdBy

updatedBy

deletedAt
```

---

# Soft Delete

A primeira versão do sistema utilizará exclusão física.

Caso necessário, poderá ser adotado Soft Delete em versões futuras.

---

# Integridade

A integridade referencial será garantida pela camada de aplicação.

Antes de criar registros relacionados, o backend deverá validar a existência do recurso pai.

Exemplo:

- Pet existente antes de registrar vacina.
- Pet existente antes de criar evento.

---

# Performance

Consultas deverão priorizar índices.

Evitar:

- scans completos;
- consultas sem filtros;
- documentos excessivamente grandes.

---

# Paginação

Todas as consultas de listagem deverão suportar paginação.

Parâmetros:

```text
page

limit
```

---

# Ordenação

Consultas deverão permitir ordenação por:

- nome;
- data;
- criação.

---

# Backup

O banco deverá possuir estratégia de backup periódico.

Requisitos:

- backup automático;
- restauração validada;
- retenção configurável.

---

# Escalabilidade

O modelo deverá permitir:

- aumento do volume de usuários;
- aumento do número de pets;
- crescimento do histórico de saúde;
- futuras integrações externas.

---

# Relação com outros documentos

Este documento complementa:

- DataModel.md
- BackendArchitecture.md
- ApiDesign.md
- SecurityArchitecture.md
- DeploymentArchitecture.md
