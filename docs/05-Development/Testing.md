# Testing

## Objetivo

Este documento descreve a estratégia de testes da plataforma PetCare.

Seu objetivo é garantir a qualidade da aplicação, reduzindo falhas, aumentando a confiabilidade das funcionalidades e permitindo uma evolução segura do sistema.

---

# Objetivos

A estratégia de testes busca:

- validar regras de negócio;
- reduzir regressões;
- garantir estabilidade;
- aumentar a confiabilidade do sistema;
- facilitar futuras evoluções.

---

# Pirâmide de Testes

A aplicação seguirá a estratégia da Pirâmide de Testes.

```text
            E2E
             ▲
     Integração
             ▲
      Unitários
```

Priorizar testes unitários, complementados por testes de integração e End-to-End quando necessário.

---

# Testes Unitários

Os testes unitários verificam componentes isolados da aplicação.

Exemplos:

- funções;
- serviços;
- casos de uso;
- validações;
- componentes React.

Objetivos:

- validar regras específicas;
- execução rápida;
- fácil manutenção.

---

# Testes de Integração

Os testes de integração verificam a comunicação entre diferentes módulos da aplicação.

Exemplos:

- API ↔ Banco de Dados;
- Controllers ↔ Use Cases;
- Frontend ↔ Backend.

Objetivos:

- validar integração entre camadas;
- identificar problemas de comunicação.

---

# Testes End-to-End (E2E)

Os testes E2E simulam o comportamento do usuário utilizando a aplicação completa.

Fluxos recomendados:

- Login;
- Cadastro;
- Cadastro de Pet;
- Registro de Vacina;
- Agendamento de Consulta;
- Atualização de Perfil.

---

# Testes de Backend

Priorizar testes para:

- Casos de uso;
- Repositórios;
- Controllers;
- Middlewares;
- Validações.

Todos os endpoints críticos devem ser testados.

---

# Testes de Frontend

Priorizar testes para:

- Componentes reutilizáveis;
- Formulários;
- Navegação;
- Hooks;
- Contextos;
- Fluxos principais da interface.

---

# Testes Manuais

Além dos testes automatizados, deverão ser realizados testes exploratórios antes de cada release.

Checklist sugerido:

- Login;
- Logout;
- Cadastro de usuário;
- Cadastro de pet;
- Registro de vacina;
- Registro de consulta;
- Cadastro de medicamentos;
- Agenda;
- Perfil.

---

# Cobertura

A cobertura de testes deve priorizar funcionalidades críticas em vez de buscar um percentual específico.

Áreas prioritárias:

- autenticação;
- regras de negócio;
- persistência;
- comunicação com a API.

---

# Ambiente de Testes

Os testes deverão utilizar ambiente isolado do ambiente de produção.

Características:

- banco de dados próprio;
- dados descartáveis;
- configuração independente.

---

# Dados de Teste

Os testes devem utilizar dados previsíveis e controlados.

Sempre que possível:

- criar dados antes da execução;
- remover dados após o teste;
- evitar dependência entre testes.

---

# Critérios de Qualidade

Antes de uma funcionalidade ser considerada concluída, ela deverá:

- implementar os requisitos definidos;
- passar pelos testes automatizados;
- passar pela validação manual;
- não introduzir regressões conhecidas.

---

# Correção de Defeitos

Ao corrigir um defeito deverá ser realizado:

1. identificação da causa;
2. correção;
3. criação ou atualização de teste para evitar recorrência;
4. validação da solução.

---

# Boas Práticas

- manter testes simples;
- evitar duplicação;
- utilizar nomes descritivos;
- testar comportamento, não implementação;
- manter independência entre testes.

---

# Evolução

A estratégia de testes deverá evoluir junto com a aplicação, aumentando gradativamente a cobertura e a automação dos principais fluxos do sistema.

---

# Relação com outros documentos

Este documento complementa:

```
- Backend.md
- Frontend.md
- ApiSpecification.md
- Deployment.md
- BackendArchitecture.md
```
