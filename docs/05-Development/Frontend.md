# Frontend Development

## Objetivo

Este documento descreve as diretrizes para o desenvolvimento do frontend da plataforma PetCare.

Seu objetivo é estabelecer padrões de organização, desenvolvimento e manutenção da aplicação, garantindo consistência, reutilização de componentes e uma boa experiência para o usuário.

---

# Stack Tecnológica

- React
- TypeScript
- Vite
- React Router
- Axios
- CSS Modules (ou Styled Components, conforme definido pelo projeto)

---

# Estrutura do Projeto

O frontend deverá ser organizado por responsabilidade.

```text
frontend/
│
├── public/
├── src/
│   ├── assets/
│   ├── components/
│   ├── layouts/
│   ├── pages/
│   ├── routes/
│   ├── services/
│   ├── hooks/
│   ├── contexts/
│   ├── utils/
│   ├── types/
│   ├── styles/
│   └── App.tsx
│
├── package.json
└── vite.config.ts
```

---

# Componentização

A interface deverá ser construída utilizando componentes reutilizáveis.

Exemplos:

- Button
- Card
- Input
- Modal
- Avatar
- Header
- Sidebar
- Navbar
- Badge

Cada componente deve possuir uma única responsabilidade.

---

# Páginas

As páginas representam funcionalidades completas da aplicação.

Exemplos:

- Login
- Dashboard
- Pets
- Vaccines
- Appointments
- Medications
- Allergies
- Profile

As páginas são responsáveis apenas pela composição dos componentes.

---

# Gerenciamento de Estado

Sempre que possível, utilizar estado local.

Para estados compartilhados utilizar:

- Context API

Caso a aplicação evolua significativamente, poderá ser adotada uma solução dedicada de gerenciamento de estado.

---

# Navegação

A navegação será realizada utilizando React Router.

Exemplo:

```text
/

/login

/dashboard

/pets

/pets/:id

/profile
```

Rotas protegidas deverão exigir autenticação.

---

# Comunicação com a API

Toda comunicação com o backend deverá ocorrer através da camada de serviços.

Exemplo:

```text
services/

auth.service.ts

pet.service.ts

vaccine.service.ts
```

As páginas não devem realizar chamadas HTTP diretamente.

---

# Tratamento de Erros

Erros deverão ser tratados de maneira consistente.

Exemplos:

- mensagens amigáveis;
- feedback visual;
- tratamento de erros de autenticação;
- páginas de erro quando necessário.

---

# Feedback ao Usuário

Sempre informar o resultado das ações realizadas.

Exemplos:

- loading;
- sucesso;
- erro;
- confirmação.

---

# Formulários

Todos os formulários deverão possuir:

- validação;
- mensagens de erro;
- campos obrigatórios destacados;
- prevenção de envio inválido.

---

# Organização dos Arquivos

Cada componente deverá possuir sua própria estrutura.

Exemplo:

```text
Button/

Button.tsx

Button.module.css

index.ts
```

---

# Convenções

## Componentes

Utilizar PascalCase.

Exemplos:

```text
PetCard

LoginForm

Navbar

UserAvatar
```

---

## Hooks

Utilizar prefixo **use**.

Exemplos:

```text
useAuth

usePets

useModal
```

---

## Arquivos

Utilizar nomes descritivos.

Evitar abreviações desnecessárias.

---

# Estilização

A interface deverá seguir o Design System definido para o projeto.

Objetivos:

- consistência visual;
- reutilização;
- responsividade;
- acessibilidade.

---

# Responsividade

A aplicação deverá funcionar adequadamente em:

- desktop;
- tablet;
- smartphone.

Layouts devem ser adaptáveis para diferentes resoluções.

---

# Acessibilidade

Sempre que possível, seguir boas práticas de acessibilidade.

Exemplos:

- HTML semântico;
- contraste adequado;
- navegação por teclado;
- textos alternativos para imagens;
- labels em formulários.

---

# Performance

Priorizar:

- componentes reutilizáveis;
- renderizações eficientes;
- carregamento otimizado;
- lazy loading quando necessário.

---

# Autenticação

O frontend deverá controlar:

- login;
- logout;
- armazenamento do token;
- proteção de rotas.

O token deverá ser enviado automaticamente nas requisições autenticadas.

---

# Organização do Código

Priorizar:

- componentes pequenos;
- alta coesão;
- baixo acoplamento;
- reutilização.

Evitar lógica de negócio diretamente na interface.

---

# Testes

Componentes críticos deverão possuir testes sempre que aplicável.

Priorizar:

- testes unitários;
- testes de integração.

---

# Evolução

Novas funcionalidades deverão manter os padrões definidos neste documento, preservando a consistência visual, arquitetural e de experiência do usuário.

---

# Relação com outros documentos

Este documento complementa:

- FrontendArchitecture.md
- DesignSystem.md
- ApiDesign.md
- ApiSpecification.md
- Testing.md
- Deployment.md
