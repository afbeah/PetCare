# Backend Architecture

## Objetivo

Este documento descreve a arquitetura do backend da plataforma PetCare.

Seu objetivo é definir a organização das camadas da aplicação, suas responsabilidades e a comunicação entre elas, promovendo uma solução modular, testável e de fácil evolução.

A arquitetura adota uma abordagem baseada em Clean Architecture simplificada, separando claramente domínio, aplicação e infraestrutura.

---

# Objetivos Arquiteturais

O backend deverá ser:

- modular;
- desacoplado;
- testável;
- escalável;
- resiliente;
- de fácil manutenção.

---

# Visão Geral

O backend é organizado nas seguintes camadas:

```text
HTTP

↓

Controllers

↓

Application (Use Cases)

↓

Domain

↓

Repositories (Interfaces)

↓

Infrastructure

↓

Database
```

Cada camada possui responsabilidades específicas e depende apenas da camada imediatamente inferior ou de abstrações.

---

# Camadas

## HTTP

Responsável por receber e responder requisições HTTP.

Responsabilidades:

- roteamento;
- autenticação inicial;
- serialização;
- desserialização;
- códigos HTTP.

---

## Controllers

Os Controllers coordenam as requisições recebidas.

Responsabilidades:

- validar entrada;
- chamar casos de uso;
- transformar respostas;
- retornar códigos HTTP apropriados.

Os Controllers não devem conter regras de negócio.

---

## Application

Também chamada de camada de Casos de Uso.

Responsabilidades:

- coordenar operações;
- aplicar regras da aplicação;
- orquestrar entidades;
- controlar transações.

Exemplos:

- RegisterUser
- AuthenticateUser
- CreatePet
- RegisterVaccine
- ScheduleEvent

---

## Domain

Representa o núcleo da aplicação.

Contém:

- entidades;
- value objects;
- regras de negócio;
- serviços de domínio;
- interfaces de repositório.

Esta camada não depende de frameworks.

---

## Infrastructure

Responsável pela implementação técnica.

Inclui:

- banco de dados;
- autenticação JWT;
- armazenamento;
- envio de e-mails;
- integração com APIs externas.

---

## Database

Responsável pela persistência das informações.

A camada de domínio nunca acessa diretamente o banco de dados.

---

# Repositórios

Os repositórios abstraem o acesso aos dados.

Exemplos:

- UserRepository
- PetRepository
- VaccineRepository
- AppointmentRepository
- MedicationRepository
- EventRepository

As implementações concretas pertencem à camada de infraestrutura.

---

# Comunicação

Fluxo padrão:

```text
Request

↓

Controller

↓

Use Case

↓

Repository Interface

↓

Repository Implementation

↓

Database

↓

Response
```

---

# Tratamento de Erros

Os erros são classificados em:

- validação;
- autenticação;
- autorização;
- domínio;
- infraestrutura;
- inesperados.

Cada categoria deverá possuir tratamento específico.

---

# Validação

As validações ocorrem em diferentes níveis.

## Entrada

Formato dos dados.

Exemplo:

- e-mail;
- senha;
- campos obrigatórios.

---

## Domínio

Regras de negócio.

Exemplo:

- pet deve possuir tutor;
- vacina deve estar vinculada a um pet.

---

# Transações

Operações que alteram múltiplos registros deverão utilizar transações para garantir consistência.

---

# Autenticação

O backend deverá suportar autenticação baseada em JWT.

Responsabilidades:

- emissão de token;
- validação;
- renovação quando aplicável.

---

# Autorização

As permissões deverão ser verificadas antes da execução dos casos de uso.

Exemplo:

Um tutor não poderá acessar informações pertencentes a outro usuário.

---

# Logs

Eventos importantes deverão ser registrados.

Exemplos:

- login;
- falhas de autenticação;
- erros inesperados;
- operações críticas.

---

# Testabilidade

A arquitetura deverá facilitar:

- testes unitários dos casos de uso;
- testes das entidades;
- testes de integração;
- testes da API.

---

# Evolução

Novas funcionalidades deverão ser implementadas preservando:

- independência do domínio;
- baixo acoplamento;
- alta coesão;
- reutilização de componentes da aplicação.

---

# Relação com outros documentos

Este documento complementa:

- ArchitectureOverview.md
- ApiDesign.md
- DatabaseDesign.md
- SecurityArchitecture.md
- TechnologyStack.md
