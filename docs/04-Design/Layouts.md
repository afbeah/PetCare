# Layouts

## Objetivo

Este documento define os layouts estruturais da plataforma PetCare.

Os layouts estabelecem a organização visual das páginas, padronizando a distribuição dos componentes da interface e promovendo consistência na experiência do usuário.

Cada layout representa um modelo reutilizável para um conjunto de telas com características semelhantes.

---

# Visão Geral

A aplicação utiliza cinco layouts principais:

- Public Layout
- App Layout
- Detail Layout
- Form Layout
- Settings Layout

Cada página da aplicação deve utilizar um desses layouts como base.

---

# Public Layout

## Finalidade

Utilizado por páginas acessíveis sem autenticação.

## Páginas

- Landing Page
- Login
- Cadastro
- Recuperação de Senha
- Redefinição de Senha

## Estrutura

────────────────────────────

Logo

Conteúdo Principal

Ações

Rodapé

────────────────────────────

## Características

- interface simples;
- foco em uma única tarefa;
- sem menu de navegação;
- conteúdo centralizado;
- responsivo.

---

# App Layout

## Finalidade

Layout principal da aplicação autenticada.

## Páginas

- Dashboard
- Lista de Pets
- Agenda
- Histórico

## Estrutura

────────────────────────────────────────

Header

────────────────────────────────────────

Menu de Navegação

────────────────────────────────────────

Área de Conteúdo

────────────────────────────────────────

Ações Flutuantes (quando necessário)

────────────────────────────────────────

## Características

- navegação permanente;
- acesso rápido às áreas principais;
- estrutura reutilizável;
- conteúdo dinâmico.

---

# Detail Layout

## Finalidade

Apresentar informações detalhadas de uma entidade.

## Páginas

- Perfil do Pet
- Consulta
- Vacina
- Medicamento
- Evento

## Estrutura

────────────────────────────

Cabeçalho

Resumo

Abas

Conteúdo

────────────────────────────

## Características

- foco em uma única entidade;
- informações agrupadas;
- navegação por seções;
- fácil edição.

---

# Form Layout

## Finalidade

Padronizar formulários de criação e edição.

## Páginas

- Novo Pet
- Editar Pet
- Nova Vacina
- Nova Consulta
- Novo Medicamento
- Novo Evento

## Estrutura

────────────────────────────

Título

Descrição

Campos

Botões

────────────────────────────

## Características

- sequência lógica;
- validação imediata;
- mensagens de erro próximas ao campo;
- confirmação clara de sucesso.

---

# Settings Layout

## Finalidade

Gerenciar configurações da conta.

## Páginas

- Perfil
- Preferências
- Segurança

## Estrutura

────────────────────────────

Menu Lateral

Conteúdo

────────────────────────────

## Características

- navegação secundária;
- organização por categorias;
- alterações independentes.

---

# Regiões da Interface

Todos os layouts poderão utilizar as seguintes regiões:

## Header

Responsável por apresentar:

- título da página;
- navegação;
- ações rápidas.

---

## Content

Área destinada ao conteúdo principal.

---

## Sidebar

Utilizada quando houver necessidade de navegação secundária.

---

## Footer

Utilizado apenas em páginas públicas.

---

## Floating Action Button

Botão destinado às principais ações da página.

Exemplos:

- Novo Pet
- Nova Consulta
- Novo Evento

---

# Responsividade

## Desktop

- navegação lateral ou superior;
- múltiplas colunas;
- maior densidade de informação.

---

## Tablet

- adaptação para duas colunas quando possível;
- reorganização dos painéis.

---

## Mobile

- navegação simplificada;
- uma coluna;
- ações acessíveis com o polegar;
- prioridade para conteúdo essencial.

---

# Estados

Cada layout deverá prever:

- carregamento;
- vazio;
- erro;
- sucesso.

---

# Princípios

Os layouts da PetCare seguem os seguintes princípios:

- consistência;
- reutilização;
- simplicidade;
- acessibilidade;
- responsividade;
- escalabilidade.
