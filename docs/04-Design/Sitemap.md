# Sitemap

## Objetivo

Este documento apresenta o mapa estrutural da plataforma PetCare.

Seu objetivo é organizar todas as páginas da aplicação, demonstrando a hierarquia entre telas e servindo como referência para UX, desenvolvimento frontend e testes.

O Sitemap representa a estrutura navegável da aplicação, independentemente da implementação.

---

# Estrutura Geral

PetCare

├── Landing Page
│
├── Autenticação
│   ├── Login
│   ├── Cadastro
│   ├── Recuperação de Senha
│   └── Redefinição de Senha
│
└── Área Autenticada
    │
    ├── Dashboard
    │
    ├── Pets
    │   ├── Lista de Pets
    │   ├── Cadastro de Pet
    │   ├── Perfil do Pet
    │   │
    │   ├── Informações Gerais
    │   ├── Carteira de Vacinação
    │   ├── Consultas
    │   ├── Medicamentos
    │   ├── Alergias
    │   ├── Histórico
    │   └── Agenda
    │
    ├── Agenda
    │   ├── Calendário
    │   ├── Eventos
    │   └── Detalhes do Evento
    │
    ├── Histórico
    │   ├── Histórico Geral
    │   ├── Vacinação
    │   ├── Consultas
    │   └── Medicamentos
    │
    ├── Perfil
    │   ├── Dados Pessoais
    │   ├── Alteração de Senha
    │   └── Preferências
    │
    └── Configurações
        ├── Notificações
        ├── Segurança
        └── Sobre
