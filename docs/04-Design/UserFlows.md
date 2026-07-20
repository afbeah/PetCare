# User Flows

## Objetivo

Este documento descreve os principais fluxos de interação da plataforma PetCare.

Os fluxos representam a sequência de ações realizadas pelos usuários para atingir um objetivo específico dentro do sistema.

Seu objetivo é servir como referência para o design da experiência do usuário, implementação das funcionalidades e definição dos testes de aceitação.

---

# Atores

## Tutor

Usuário responsável pelo gerenciamento das informações dos seus animais de estimação.

---

# UF-001 - Primeiro Acesso

## Objetivo

Permitir que um novo usuário crie uma conta e acesse a plataforma.

### Fluxo

Landing Page

↓

Cadastro

↓

Preenchimento dos Dados

↓

Validação

↓

Conta Criada

↓

Login

↓

Dashboard

---

# UF-002 - Login

## Objetivo

Permitir que um usuário autenticado acesse sua conta.

### Fluxo

Login

↓

Informar Credenciais

↓

Validação

↓

Dashboard

---

# UF-003 - Cadastro de Pet

## Objetivo

Permitir registrar um novo animal.

### Fluxo

Dashboard

↓

Pets

↓

Novo Pet

↓

Preenchimento dos Dados

↓

Salvar

↓

Perfil do Pet

---

# UF-004 - Consulta do Perfil do Pet

## Objetivo

Visualizar todas as informações relacionadas ao animal.

### Fluxo

Dashboard

↓

Pets

↓

Selecionar Pet

↓

Perfil do Pet

---

# UF-005 - Registro de Vacinação

## Objetivo

Adicionar uma vacina ao histórico do pet.

### Fluxo

Perfil do Pet

↓

Carteira de Vacinação

↓

Nova Vacina

↓

Preencher Informações

↓

Salvar

↓

Carteira Atualizada

---

# UF-006 - Registro de Consulta

## Objetivo

Adicionar uma consulta veterinária.

### Fluxo

Perfil do Pet

↓

Consultas

↓

Nova Consulta

↓

Informações da Consulta

↓

Salvar

↓

Histórico Atualizado

---

# UF-007 - Registro de Medicamento

## Objetivo

Registrar um medicamento.

### Fluxo

Perfil do Pet

↓

Medicamentos

↓

Novo Medicamento

↓

Informações

↓

Salvar

↓

Lista Atualizada

---

# UF-008 - Registro de Alergia

## Objetivo

Cadastrar uma alergia.

### Fluxo

Perfil do Pet

↓

Alergias

↓

Nova Alergia

↓

Informações

↓

Salvar

↓

Lista Atualizada

---

# UF-009 - Agendamento de Evento

## Objetivo

Cadastrar um compromisso.

### Fluxo

Agenda

↓

Novo Evento

↓

Selecionar Pet

↓

Informações

↓

Salvar

↓

Calendário

---

# UF-010 - Consulta do Histórico

## Objetivo

Consultar todo o histórico de saúde do pet.

### Fluxo

Dashboard

↓

Pets

↓

Perfil do Pet

↓

Histórico

↓

Visualizar Registros

---

# Fluxos Secundários

Além dos fluxos principais, o sistema deverá permitir:

- editar informações;
- excluir registros;
- pesquisar pets;
- pesquisar eventos;
- alterar perfil;
- alterar senha;
- redefinir senha.

---

# Princípios

Os fluxos da PetCare deverão seguir os seguintes princípios:

- menor número possível de etapas;
- navegação consistente;
- feedback contínuo ao usuário;
- prevenção de erros;
- facilidade de retorno;
- conclusão clara de cada operação.
