# Use Cases

## Objetivo

Este documento descreve os principais casos de uso da plataforma PetCare.

Os casos de uso representam as interações entre os atores e o sistema para alcançar objetivos específicos, servindo como base para implementação, testes e validação dos requisitos funcionais.

---

# Atores

## Tutor

Usuário responsável pelo gerenciamento das informações de um ou mais pets.

---

# UC-001 - Realizar Cadastro

## Objetivo

Permitir que um novo usuário crie uma conta na plataforma.

### Atores

- Tutor

### Pré-condições

- O usuário não possui uma conta cadastrada.

### Fluxo Principal

1. O usuário acessa a tela de cadastro.
2. O sistema solicita as informações obrigatórias.
3. O usuário preenche os dados.
4. O sistema valida as informações.
5. O sistema cria a conta.
6. O sistema confirma o cadastro.

### Pós-condições

O usuário passa a possuir uma conta válida.

---

# UC-002 - Realizar Login

## Objetivo

Permitir acesso à plataforma.

### Pré-condições

- Usuário previamente cadastrado.

### Fluxo Principal

1. Informar credenciais.
2. Validar credenciais.
3. Criar sessão autenticada.
4. Redirecionar para a página inicial.

### Pós-condições

Usuário autenticado.

---

# UC-003 - Cadastrar Pet

## Objetivo

Permitir registrar um novo pet.

### Pré-condições

- Usuário autenticado.

### Fluxo Principal

1. Selecionar "Novo Pet".
2. Informar dados do pet.
3. Confirmar cadastro.
4. Salvar informações.

### Pós-condições

Pet disponível para gerenciamento.

---

# UC-004 - Atualizar Informações do Pet

## Objetivo

Permitir alterar informações de um pet.

### Pré-condições

- Pet existente.

### Fluxo Principal

1. Selecionar pet.
2. Editar informações.
3. Salvar alterações.

### Pós-condições

Dados atualizados.

---

# UC-005 - Registrar Vacinação

## Objetivo

Registrar uma vacina aplicada ao pet.

### Pré-condições

- Pet cadastrado.

### Fluxo Principal

1. Selecionar pet.
2. Acessar carteira de vacinação.
3. Adicionar registro.
4. Informar dados da vacina.
5. Confirmar registro.

### Pós-condições

Vacina adicionada ao histórico.

---

# UC-006 - Registrar Consulta Veterinária

## Objetivo

Registrar uma consulta realizada.

### Pré-condições

- Pet cadastrado.

### Fluxo Principal

1. Selecionar pet.
2. Abrir histórico de consultas.
3. Criar novo registro.
4. Informar dados da consulta.
5. Salvar.

### Pós-condições

Consulta registrada.

---

# UC-007 - Registrar Medicamento

## Objetivo

Registrar um medicamento utilizado pelo pet.

### Pré-condições

- Pet cadastrado.

### Fluxo Principal

1. Selecionar pet.
2. Abrir medicamentos.
3. Criar registro.
4. Informar medicamento.
5. Salvar.

### Pós-condições

Medicamento registrado.

---

# UC-008 - Registrar Alergia

## Objetivo

Registrar uma alergia conhecida.

### Pré-condições

- Pet cadastrado.

### Fluxo Principal

1. Selecionar pet.
2. Abrir alergias.
3. Adicionar registro.
4. Salvar.

### Pós-condições

Alergia registrada.

---

# UC-009 - Criar Evento

## Objetivo

Adicionar um compromisso relacionado ao pet.

### Pré-condições

- Pet cadastrado.

### Fluxo Principal

1. Selecionar pet.
2. Abrir agenda.
3. Criar evento.
4. Definir data.
5. Salvar.

### Pós-condições

Evento disponível na agenda.

---

# UC-010 - Consultar Histórico do Pet

## Objetivo

Visualizar todas as informações relacionadas ao pet.

### Pré-condições

- Pet existente.

### Fluxo Principal

1. Selecionar pet.
2. Abrir histórico.
3. Visualizar registros.

### Pós-condições

Nenhuma alteração é realizada.
