# Product Scope

## Objetivo

Este documento define o escopo funcional da plataforma PetCare.

Seu objetivo é estabelecer os limites do produto, identificando quais problemas serão resolvidos, quais funcionalidades fazem parte da solução e quais capacidades não serão contempladas na versão atual.

O escopo definido neste documento serve como referência para os requisitos, arquitetura, design e desenvolvimento do sistema.

---

# Objetivo do Produto

A PetCare tem como objetivo disponibilizar uma plataforma digital para gerenciamento das informações relacionadas aos cuidados com animais de estimação.

O sistema deve permitir que tutores registrem, consultem e acompanhem informações relevantes sobre seus pets em um ambiente único e organizado.

---

# Escopo Funcional

A primeira versão da plataforma contempla funcionalidades relacionadas aos seguintes módulos.

## Gestão de Usuários

- Cadastro de usuários;
- Autenticação;
- Recuperação de senha;
- Gerenciamento do perfil do tutor.

---

## Gestão de Pets

- Cadastro de pets;
- Edição de informações;
- Exclusão de registros;
- Visualização dos pets cadastrados.

---

## Saúde do Pet

- Registro de vacinas;
- Histórico de vacinação;
- Registro de consultas;
- Registro de medicamentos;
- Registro de alergias;
- Histórico geral de saúde.

---

## Agenda

- Cadastro de eventos;
- Lembretes;
- Próximas vacinas;
- Próximas consultas;
- Administração de medicamentos.

---

## Consulta das Informações

O tutor poderá visualizar de forma organizada todas as informações relacionadas a cada pet, permitindo acompanhamento contínuo do histórico de cuidados.

---

# Fora do Escopo

As funcionalidades abaixo não fazem parte da primeira versão da plataforma.

## Comercial

- Marketplace;
- Loja virtual;
- Venda de produtos.

---

## Social

- Rede social;
- Comunidades;
- Compartilhamento entre usuários;
- Feed de publicações.

---

## Serviços

- Agendamento online em clínicas;
- Telemedicina veterinária;
- Pet sitter;
- Hospedagem para pets;
- Passeadores.

---

## Inteligência Artificial

- Diagnóstico automatizado;
- Recomendações clínicas;
- Assistente virtual.

---

## Integrações Externas

- Dispositivos IoT;
- Wearables para pets;
- Integrações com clínicas veterinárias;
- Integrações com laboratórios.

---

# Premissas

Durante o desenvolvimento do MVP considera-se que:

- o tutor é o principal usuário da plataforma;
- cada pet possui pelo menos um tutor responsável;
- um tutor pode possuir vários pets;
- todas as informações cadastradas pertencem ao tutor responsável;
- o sistema deve permitir evolução incremental.

---

# Restrições

O desenvolvimento da primeira versão possui as seguintes restrições:

- implementação apenas das funcionalidades essenciais;
- backend reduzido às necessidades do MVP;
- ausência de integrações externas;
- foco em validação funcional da plataforma.

---

# Limites do Produto

O sistema não substitui acompanhamento veterinário.

A PetCare atua como ferramenta de organização, consulta e gerenciamento das informações relacionadas aos cuidados do animal.

Toda decisão clínica permanece sob responsabilidade de profissionais habilitados.

---

# Critérios de Conclusão

O escopo da primeira versão será considerado concluído quando permitir que um tutor:

- crie sua conta;
- realize autenticação;
- cadastre um ou mais pets;
- mantenha informações atualizadas sobre seus animais;
- registre eventos relacionados à saúde;
- consulte o histórico completo de cuidados;
- acompanhe lembretes e compromissos futuros.

---

# Evolução

Novos módulos poderão ser incorporados em versões futuras sem alterar os objetivos fundamentais da plataforma.

A arquitetura deverá permitir expansão gradual do produto preservando a organização e a manutenibilidade do sistema.
