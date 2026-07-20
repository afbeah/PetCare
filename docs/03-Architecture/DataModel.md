# Data Model

## Objetivo

Este documento descreve o modelo conceitual de dados da plataforma PetCare.

Seu objetivo é definir as entidades do domínio, seus atributos, relacionamentos e regras de integridade, servindo como base para a implementação da camada de persistência e para a comunicação entre frontend e backend.

O modelo apresentado é independente da tecnologia de banco de dados utilizada.

---

# Princípios

O modelo de dados deverá:

- representar fielmente o domínio;
- evitar redundância desnecessária;
- facilitar evolução do sistema;
- manter consistência entre entidades;
- permitir escalabilidade.

---

# Visão Geral

A plataforma é composta pelas seguintes entidades principais:

- User
- Pet
- Vaccine
- Appointment
- Medication
- Allergy
- Event

---

# Entidade: User

Representa o tutor responsável pelos pets.

## Atributos

| Campo | Tipo | Obrigatório |
|--------|------|-------------|
| id | UUID | Sim |
| name | String | Sim |
| email | String | Sim |
| password | String | Sim |
| createdAt | DateTime | Sim |
| updatedAt | DateTime | Sim |

---

## Relacionamentos

Um usuário pode possuir vários pets.

```
User
 1
 │
 │
 N
Pet
```

---

# Entidade: Pet

Representa um animal cadastrado.

## Atributos

| Campo | Tipo |
|--------|------|
| id | UUID |
| ownerId | UUID |
| name | String |
| species | Enum |
| breed | String |
| sex | Enum |
| birthDate | Date |
| weight | Decimal |
| photo | String |
| notes | String |
| createdAt | DateTime |
| updatedAt | DateTime |

---

## Relacionamentos

Um Pet possui:

- Vacinas
- Consultas
- Medicamentos
- Alergias
- Eventos

---

# Entidade: Vaccine

Representa uma vacinação.

## Atributos

| Campo | Tipo |
|--------|------|
| id | UUID |
| petId | UUID |
| name | String |
| applicationDate | Date |
| nextDose | Date |
| veterinarian | String |
| notes | String |

---

## Relacionamentos

```
Pet

1

│

N

Vaccine
```

---

# Entidade: Appointment

Representa uma consulta veterinária.

## Atributos

| Campo | Tipo |
|--------|------|
| id | UUID |
| petId | UUID |
| date | DateTime |
| veterinarian | String |
| clinic | String |
| diagnosis | String |
| notes | String |

---

# Entidade: Medication

Representa um medicamento.

## Atributos

| Campo | Tipo |
|--------|------|
| id | UUID |
| petId | UUID |
| name | String |
| dosage | String |
| frequency | String |
| startDate | Date |
| endDate | Date |
| observations | String |

---

# Entidade: Allergy

Representa uma alergia.

## Atributos

| Campo | Tipo |
|--------|------|
| id | UUID |
| petId | UUID |
| name | String |
| severity | Enum |
| description | String |

---

# Entidade: Event

Representa um compromisso na agenda.

## Atributos

| Campo | Tipo |
|--------|------|
| id | UUID |
| petId | UUID |
| title | String |
| description | String |
| date | DateTime |
| type | Enum |
| completed | Boolean |

---

# Relacionamentos

```
User

│ 1

│

└───────────────┐

                │

                │ N

              Pet

      ├──────────────┐

      │              │

      │              │

      ▼              ▼

 Vaccine      Appointment

      │

      ▼

 Medication

      │

      ▼

 Allergy

      │

      ▼

 Event
```

---

# Cardinalidade

| Origem | Destino | Cardinalidade |
|---------|----------|---------------|
| User | Pet | 1:N |
| Pet | Vaccine | 1:N |
| Pet | Appointment | 1:N |
| Pet | Medication | 1:N |
| Pet | Allergy | 1:N |
| Pet | Event | 1:N |

---

# Regras de Integridade

## User

- E-mail deve ser único.
- Senha deve ser armazenada criptografada.

---

## Pet

- Todo pet pertence a um usuário.
- Um pet não pode existir sem tutor.

---

## Vaccine

- Toda vacina pertence a um pet.
- A data de aplicação não pode ser futura, salvo registros planejados.

---

## Appointment

- Toda consulta pertence a um pet.

---

## Medication

- Todo medicamento pertence a um pet.

---

## Allergy

- Toda alergia pertence a um pet.

---

## Event

- Todo evento pertence a um pet.

---

# Convenções

- IDs são UUID.
- Datas seguem ISO-8601.
- Todos os registros possuem data de criação e atualização quando aplicável.

---

# Evolução

Novas entidades deverão manter os princípios deste modelo, preservando consistência, baixo acoplamento e alinhamento com as regras de negócio da plataforma.
