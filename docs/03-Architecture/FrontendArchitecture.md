# Frontend Architecture

## Objetivo

Este documento descreve a arquitetura do frontend da plataforma PetCare.

Seu objetivo é definir como a interface da aplicação será organizada, estabelecendo padrões para estrutura de pastas, componentes, gerenciamento de estado, navegação e comunicação com a API.

A arquitetura busca promover reutilização, escalabilidade, baixo acoplamento e facilidade de manutenção.

---

# Objetivos

O frontend deverá ser:

- modular;
- reutilizável;
- responsivo;
- acessível;
- testável;
- escalável.

---

# Arquitetura Geral

O frontend é dividido em cinco grandes responsabilidades:

- Presentation
- Application
- Domain
- Infrastructure
- Shared

```text
src
│
├── app
├── pages
├── features
├── components
├── hooks
├── services
├── layouts
├── routes
├── assets
├── styles
├── utils
└── types
```

A organização privilegia o domínio da aplicação em vez da tecnologia utilizada.

---

# Camada de Presentation

Responsável pela renderização da interface.

Inclui:

- páginas;
- componentes;
- layouts;
- estilos;
- navegação.

Essa camada não deve conter regras de negócio.

---

# Camada de Application

Responsável por coordenar os casos de uso do frontend.

Exemplos:

- cadastrar pet;
- editar pet;
- autenticar usuário;
- registrar vacina.

Essa camada orquestra chamadas para serviços e atualiza o estado da interface.

---

# Camada de Domain

Representa os conceitos de negócio compartilhados pelo frontend.

Exemplos:

- Pet
- User
- Vaccine
- Appointment
- Medication

Também pode conter validações de domínio reutilizáveis na interface.

---

# Camada de Infrastructure

Responsável pela comunicação com sistemas externos.

Inclui:

- cliente HTTP;
- autenticação;
- armazenamento local;
- interceptadores;
- integração com APIs.

---

# Shared

Contém recursos reutilizáveis por toda a aplicação.

Exemplos:

- componentes genéricos;
- hooks;
- utilitários;
- constantes;
- tipos;
- helpers.

---

# Estrutura por Funcionalidade

Sempre que possível, os módulos devem ser organizados por domínio.

Exemplo:

```text
features
│
├── authentication
├── pets
├── vaccines
├── appointments
├── medications
├── agenda
└── profile
```

Cada funcionalidade deve concentrar seus próprios componentes, serviços, hooks e testes.

---

# Componentes

Os componentes devem possuir responsabilidade única.

Categorias:

- UI Components
- Feature Components
- Layout Components

---

## UI Components

Componentes reutilizáveis.

Exemplos:

- Button
- Card
- Input
- Modal

---

## Feature Components

Relacionados a um domínio específico.

Exemplos:

- PetCard
- VaccineTimeline
- AppointmentList

---

## Layout Components

Responsáveis pela estrutura visual das páginas.

Exemplos:

- AppLayout
- PublicLayout
- DetailLayout

---

# Gerenciamento de Estado

O estado da aplicação será dividido em:

## Estado Global

Utilizado apenas quando necessário.

Exemplos:

- usuário autenticado;
- tema;
- configurações.

---

## Estado Local

Preferencialmente utilizado para formulários e interações da interface.

---

## Estado Remoto

Representa dados provenientes da API.

Esses dados devem possuir tratamento específico para:

- carregamento;
- erro;
- atualização;
- cache.

---

# Comunicação com API

Toda comunicação deverá ocorrer através de uma camada de serviços.

Os componentes nunca deverão realizar chamadas HTTP diretamente.

Fluxo:

```text
Component

↓

Hook

↓

Service

↓

HTTP Client

↓

API
```

---

# Navegação

A navegação deverá ser centralizada em um módulo de rotas.

Responsabilidades:

- rotas públicas;
- rotas privadas;
- proteção por autenticação;
- redirecionamentos.

---

# Tratamento de Erros

Os erros deverão ser tratados em níveis diferentes:

- erro de validação;
- erro de comunicação;
- erro inesperado.

Cada categoria deve fornecer feedback apropriado ao usuário.

---

# Responsividade

A arquitetura deve favorecer componentes adaptáveis, evitando duplicação entre versões desktop e mobile.

---

# Acessibilidade

Todos os componentes deverão respeitar as diretrizes definidas em `Accessibility.md`.

---

# Testabilidade

A arquitetura deverá facilitar:

- testes unitários de componentes;
- testes de hooks;
- testes de integração;
- testes end-to-end.

---

# Princípios

O frontend da PetCare segue os princípios:

- separação de responsabilidades;
- composição de componentes;
- reutilização;
- baixo acoplamento;
- alta coesão;
- previsibilidade;
- escalabilidade.
