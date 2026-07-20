# Domain Model

## Objetivo

Este documento apresenta o modelo conceitual da plataforma PetCare.

Seu objetivo é identificar as principais entidades do domínio, seus relacionamentos e responsabilidades, estabelecendo uma linguagem comum entre produto, arquitetura e desenvolvimento.

O Domain Model representa a visão do negócio, não a estrutura do banco de dados.

---

# Visão Geral

A PetCare possui como elemento central o **Pet**.

Todos os registros da plataforma estão relacionados direta ou indiretamente a um pet, permitindo que seu histórico de saúde seja acompanhado de forma completa.

Os tutores são responsáveis pelo gerenciamento dessas informações.

---

# Entidades do Domínio

## User

Representa um usuário autenticado na plataforma.

### Responsabilidades

- autenticar-se no sistema;
- gerenciar seu perfil;
- administrar seus pets;
- consultar informações cadastradas.

---

## Pet

Representa um animal de estimação cadastrado.

É a principal entidade do domínio.

### Responsabilidades

- armazenar informações gerais;
- agrupar registros de saúde;
- manter histórico clínico.

---

## Vaccine Record

Representa um registro de vacinação.

### Responsabilidades

- armazenar vacina aplicada;
- registrar data de aplicação;
- registrar próximas doses quando existirem.

---

## Medical Appointment

Representa uma consulta veterinária.

### Responsabilidades

- registrar atendimentos;
- armazenar observações;
- compor histórico clínico.

---

## Medication

Representa um medicamento associado ao pet.

### Responsabilidades

- registrar utilização;
- armazenar período de administração;
- manter histórico.

---

## Allergy

Representa uma alergia conhecida do pet.

### Responsabilidades

- registrar restrições;
- apoiar consultas futuras.

---

## Event

Representa um compromisso relacionado aos cuidados do pet.

### Responsabilidades

- organizar calendário;
- gerar lembretes;
- registrar eventos futuros.

---

# Relacionamentos

## User → Pet

Um usuário pode possuir vários pets.

Todo pet deve possuir pelo menos um tutor.

---

## Pet → Vaccine Record

Um pet pode possuir vários registros de vacinação.

Cada registro pertence a apenas um pet.

---

## Pet → Medical Appointment

Um pet pode possuir várias consultas veterinárias.

Cada consulta pertence a apenas um pet.

---

## Pet → Medication

Um pet pode possuir vários medicamentos registrados.

Cada medicamento pertence a apenas um pet.

---

## Pet → Allergy

Um pet pode possuir várias alergias cadastradas.

Cada alergia pertence exclusivamente ao pet.

---

## Pet → Event

Um pet pode possuir diversos eventos.

Cada evento está associado a apenas um pet.

---

# Agregado Principal

O agregado principal do domínio é o **Pet**.

Todas as operações relacionadas à saúde do animal são realizadas através dele.

As demais entidades representam informações dependentes desse agregado.

---

# Identidade das Entidades

As seguintes entidades possuem identidade própria:

- User
- Pet
- Vaccine Record
- Medical Appointment
- Medication
- Allergy
- Event

---

# Objetos de Valor

Na versão atual do sistema, não foram definidos objetos de valor específicos.

Eles poderão ser incorporados em futuras evoluções do domínio.

---

# Considerações

O modelo de domínio apresentado neste documento representa os conceitos centrais da plataforma e deverá servir como base para:

- modelo de dados;
- especificação das APIs;
- implementação das regras de negócio;
- arquitetura da aplicação.
