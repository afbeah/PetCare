# Navigation

## Objetivo

Este documento descreve a estrutura de navegação da plataforma PetCare.

Seu objetivo é definir como os usuários transitam entre as diferentes áreas do sistema, estabelecendo uma navegação consistente, previsível e centrada nas principais jornadas do produto.

---

# Estrutura Geral

A navegação da plataforma está organizada em dois níveis:

- Navegação Primária
- Navegação Contextual

---

# Navegação Primária

A navegação primária representa as principais áreas acessíveis pelo usuário autenticado.

## Dashboard

Página inicial da plataforma.

Permite acesso rápido aos principais recursos do sistema.

---

## Pets

Área responsável pelo gerenciamento dos animais cadastrados.

---

## Agenda

Área destinada ao acompanhamento de eventos e compromissos.

---

## Histórico

Área para consulta das informações registradas.

---

## Perfil

Área destinada ao gerenciamento da conta do usuário.

---

# Navegação Contextual

A navegação contextual depende da tela atualmente acessada.

Exemplo:

Pet

↓

Vacinas

↓

Detalhes da Vacina

ou

Pet

↓

Consultas

↓

Detalhes da Consulta

---

# Fluxo de Acesso

Usuário

↓

Login

↓

Dashboard

↓

Selecionar Pet

↓

Perfil do Pet

↓

Funcionalidade desejada

---

# Fluxo do Dashboard

O Dashboard funciona como ponto central da navegação.

A partir dele o usuário pode acessar:

- Lista de Pets
- Agenda
- Histórico
- Perfil
- Configurações

---

# Fluxo dos Pets

Lista de Pets

↓

Selecionar Pet

↓

Perfil do Pet

↓

Informações Gerais

↓

Vacinas

↓

Consultas

↓

Medicamentos

↓

Alergias

↓

Agenda

---

# Fluxo da Agenda

Agenda

↓

Calendário

↓

Evento

↓

Detalhes

---

# Fluxo do Histórico

Histórico

↓

Pet

↓

Tipo de Registro

↓

Detalhes

---

# Fluxo do Perfil

Perfil

↓

Dados Pessoais

↓

Segurança

↓

Preferências

---

# Navegação Global

Durante toda a sessão autenticada o usuário deverá possuir acesso rápido às principais áreas do sistema.

A navegação principal deverá permanecer consistente em todas as telas.

---

# Breadcrumb

Sempre que aplicável, o sistema deverá apresentar o caminho percorrido pelo usuário.

Exemplo:

Dashboard

>

Pets

>

Thor

>

Vacinas

>

Detalhes

---

# Estados de Navegação

O sistema deverá preservar o contexto do usuário durante sua navegação.

Ao retornar para uma tela anterior, sempre que possível, deverão ser mantidos:

- filtros;
- paginação;
- seleção atual;
- posição da rolagem.

---

# Princípios

A navegação da PetCare deverá seguir os seguintes princípios:

- previsibilidade;
- consistência;
- baixo número de cliques;
- foco na tarefa;
- redução de carga cognitiva;
- fácil aprendizagem.
