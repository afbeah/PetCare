# Backend Development

## Objetivo

Este documento descreve as diretrizes para o desenvolvimento do backend da plataforma PetCare.

Seu objetivo é estabelecer uma organização consistente do código, facilitar a manutenção da aplicação e garantir que novas funcionalidades sejam implementadas seguindo os mesmos padrões arquiteturais.

---

# Stack Tecnológica

- Go
- Echo Framework
- MongoDB
- JWT
- Docker

---

# Estrutura do Projeto

A organização do backend segue uma arquitetura em camadas.

```text
backend/
│
├── cmd/
│
├── internal/
│   ├── application/
│   ├── domain/
│   ├── infrastructure/
│   └── interfaces/
│
├── configs/
│
├── docs/
│
├── scripts/
│
├── tests/
│
└── main.go
```

Cada diretório possui responsabilidades bem definidas.

---

# Organização das Camadas

## Domain

Contém as regras centrais do negócio.

Exemplos:

- entidades;
- interfaces;
- regras de domínio;
- validações de negócio.

A camada Domain não deve depender de nenhuma outra camada.

---

## Application

Responsável pelos casos de uso da aplicação.

Exemplos:

- CreatePet
- UpdatePet
- RegisterVaccine
- ScheduleAppointment

Os casos de uso coordenam o fluxo da aplicação utilizando as entidades do domínio.

---

## Infrastructure

Responsável pela implementação dos serviços externos.

Exemplos:

- MongoDB
- JWT
- armazenamento de arquivos
- serviços de e-mail

Essa camada implementa as interfaces definidas no domínio.

---

## Interfaces

Responsável pela comunicação com o mundo externo.

Exemplos:

- Controllers
- Middlewares
- Rotas
- DTOs

---

# Organização das Rotas

As rotas deverão ser agrupadas por recurso.

Exemplo:

```text
/auth

/users

/pets

/vaccines

/appointments

/medications

/allergies

/events
```

---

# Controllers

Os controllers possuem apenas responsabilidades relacionadas ao protocolo HTTP.

Responsabilidades:

- receber requisições;
- validar entrada;
- chamar o caso de uso;
- retornar resposta.

Os controllers não devem conter regras de negócio.

---

# Casos de Uso

Cada funcionalidade deverá possuir um caso de uso específico.

Exemplos:

```text
CreatePet

UpdatePet

DeletePet

RegisterVaccine

ScheduleAppointment
```

Os casos de uso concentram as regras da aplicação.

---

# Repositórios

O acesso ao banco de dados deverá ocorrer exclusivamente através de repositórios.

Exemplo:

```text
PetRepository

UserRepository

VaccineRepository
```

Nenhuma consulta ao banco deverá ser realizada diretamente nos controllers.

---

# DTOs

DTOs são utilizados para transportar dados entre as camadas.

Tipos:

- Request DTO
- Response DTO

Evitar exposição direta das entidades do domínio.

---

# Tratamento de Erros

Todos os erros deverão ser tratados de forma centralizada.

As respostas da API seguirão um formato padronizado.

Exemplo:

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Validation failed."
  }
}
```

---

# Validação

Toda entrada deverá ser validada antes da execução dos casos de uso.

Exemplos:

- campos obrigatórios;
- formatos;
- tamanhos;
- datas;
- UUIDs.

---

# Autenticação

Endpoints protegidos deverão validar o JWT antes da execução.

Fluxo:

```text
Request

↓

JWT Middleware

↓

Controller

↓

Use Case
```

---

# Configurações

Configurações da aplicação deverão ser carregadas por variáveis de ambiente.

Exemplos:

```text
DATABASE_URL

JWT_SECRET

PORT

LOG_LEVEL
```

---

# Logs

Eventos importantes deverão ser registrados.

Exemplos:

- inicialização da aplicação;
- autenticação;
- erros;
- operações críticas.

Logs não devem armazenar informações sensíveis.

---

# Convenções

## Nomes

Utilizar nomes claros e descritivos.

Exemplos:

```text
CreatePet

PetRepository

UpdateAppointment
```

Evitar abreviações desnecessárias.

---

## Funções

Cada função deverá possuir apenas uma responsabilidade.

Funções longas deverão ser refatoradas.

---

## Arquivos

Cada arquivo deverá representar uma única responsabilidade.

---

## Dependências

As dependências deverão ser injetadas sempre que possível.

Evitar acoplamento entre componentes.

---

# Boas Práticas

- seguir princípios SOLID;
- manter baixo acoplamento;
- favorecer alta coesão;
- evitar duplicação de código;
- escrever código legível;
- documentar comportamentos complexos.

---

# Testes

Toda funcionalidade deverá possuir testes sempre que aplicável.

Priorizar:

- testes unitários;
- testes de integração.

---

# Evolução

Novas funcionalidades deverão respeitar a arquitetura definida para o projeto, preservando a separação de responsabilidades e a consistência entre as camadas.

---

# Relação com outros documentos

Este documento complementa:

- BackendArchitecture.md
- ApiDesign.md
- ApiSpecification.md
- DatabaseDesign.md
- Testing.md
- Deployment.md
