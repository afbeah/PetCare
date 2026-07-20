# Components

## Objetivo

Este documento define a biblioteca de componentes da plataforma PetCare.

Os componentes representam elementos reutilizáveis da interface, responsáveis por garantir consistência visual, padronização da experiência do usuário e reutilização durante o desenvolvimento.

Cada componente possui uma responsabilidade única e pode ser utilizado em diferentes partes da aplicação.

---

# Organização

Os componentes estão divididos em cinco categorias:

- Foundations
- Inputs
- Navigation
- Data Display
- Feedback

---

# Foundations

## Button

Responsável por executar ações.

### Variações

- Primary
- Secondary
- Outline
- Text
- Danger

### Estados

- Default
- Hover
- Active
- Focus
- Disabled
- Loading

---

## Icon Button

Botão composto apenas por um ícone.

### Exemplos

- Editar
- Excluir
- Compartilhar
- Favoritar
- Voltar

---

## Card

Agrupa informações relacionadas.

### Utilização

- Pet
- Consulta
- Vacina
- Evento
- Medicamento

---

## Avatar

Representa visualmente um usuário ou pet.

### Variações

- Imagem
- Inicial
- Placeholder

---

## Badge

Destaca informações curtas.

### Exemplos

- Vacina Pendente
- Em Tratamento
- Concluído
- Hoje

---

## Divider

Separador visual entre conteúdos.

---

# Inputs

## Text Field

Entrada de texto.

### Tipos

- Texto
- Email
- Senha
- Telefone

---

## Text Area

Campos para textos longos.

---

## Select

Lista de opções.

---

## Checkbox

Seleção múltipla.

---

## Radio Group

Seleção única.

---

## Switch

Ativar ou desativar uma configuração.

---

## Date Picker

Seleção de datas.

---

## Search Bar

Pesquisa de informações.

---

# Navigation

## App Bar

Cabeçalho principal da aplicação.

---

## Bottom Navigation

Navegação principal em dispositivos móveis.

Itens:

- Dashboard
- Pets
- Agenda
- Perfil

---

## Sidebar

Navegação lateral para telas maiores.

---

## Breadcrumb

Exibe o caminho atual da navegação.

---

## Tabs

Alternância entre seções.

Exemplo:

- Vacinas
- Consultas
- Medicamentos
- Histórico

---

## Menu

Lista de ações.

---

# Data Display

## Pet Card

Resumo de um pet.

### Informações

- Foto
- Nome
- Espécie
- Idade

---

## Vaccine Card

Resumo de uma vacinação.

---

## Appointment Card

Resumo de uma consulta.

---

## Medication Card

Resumo de um medicamento.

---

## Event Card

Resumo de um compromisso.

---

## Timeline

Apresentação cronológica de eventos.

Utilização:

- Histórico do Pet
- Consultas
- Vacinas

---

## Calendar

Visualização mensal dos eventos.

---

## List

Apresentação sequencial de informações.

---

## Table

Exibição tabular para telas administrativas.

---

# Feedback

## Alert

Comunicação de informações importantes.

Tipos:

- Success
- Warning
- Error
- Info

---

## Toast

Notificação temporária.

---

## Modal

Confirmações e ações críticas.

---

## Dialog

Solicitação de confirmação do usuário.

---

## Empty State

Apresentado quando não existem informações.

Exemplo:

"Nenhum pet cadastrado."

---

## Loading

Representa carregamento.

Variações:

- Skeleton
- Spinner

---

## Error State

Apresenta falhas da operação.

---

# Componentes Compostos

Os componentes abaixo são formados por outros componentes menores.

## Pet Profile

Composto por:

- Avatar
- Informações Gerais
- Tabs
- Cards

---

## Dashboard Summary

Composto por:

- Cards
- Badges
- Timeline
- Calendar

---

## Appointment Timeline

Composto por:

- Timeline
- Event Cards

---

## Vaccine History

Composto por:

- Timeline
- Vaccine Cards

---

# Convenções

Todos os componentes deverão:

- possuir estados bem definidos;
- ser reutilizáveis;
- ser independentes;
- suportar acessibilidade;
- ser responsivos;
- seguir o Design System da aplicação.

---

# Estados Globais

Todo componente interativo deverá prever, quando aplicável:

- Default
- Hover
- Focus
- Active
- Disabled
- Loading
- Error
- Success

---

# Princípios

A biblioteca de componentes da PetCare segue os princípios de:

- reutilização;
- consistência;
- simplicidade;
- acessibilidade;
- modularidade;
- escalabilidade.
