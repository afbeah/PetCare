# Accessibility

## Objetivo

Este documento estabelece as diretrizes de acessibilidade da plataforma PetCare.

Seu objetivo é garantir que a aplicação possa ser utilizada pelo maior número possível de pessoas, independentemente de suas capacidades físicas, cognitivas ou tecnológicas.

A PetCare deverá seguir como referência as recomendações da WCAG 2.2 nível AA.

---

# Princípios

Toda interface da PetCare deve ser:

- Perceptível
- Operável
- Compreensível
- Robusta

---

# Navegação por Teclado

Toda funcionalidade deverá ser utilizável sem mouse.

O usuário deverá conseguir:

- navegar entre elementos utilizando TAB;
- retornar utilizando Shift + TAB;
- ativar botões utilizando Enter ou Space;
- fechar modais utilizando ESC.

---

# Foco

Todo elemento interativo deverá possuir foco visível.

O foco nunca poderá ser removido utilizando CSS.

O indicador de foco deverá possuir contraste suficiente.

---

# Contraste

A interface deverá respeitar contraste mínimo conforme WCAG.

Exemplos:

- texto normal ≥ 4.5:1
- texto grande ≥ 3:1
- componentes gráficos ≥ 3:1

---

# Tipografia

A tipografia deve favorecer a leitura.

Recomendações:

- evitar textos pequenos;
- evitar blocos muito largos;
- utilizar espaçamento confortável.

---

# Cores

Nenhuma informação poderá depender exclusivamente de cor.

Exemplo:

✔ Ícone + Cor

✘ Apenas Vermelho

---

# Botões

Todos os botões deverão possuir:

- texto descritivo;
- área mínima de toque de 44x44px;
- estado de foco;
- estado desabilitado claramente identificado.

---

# Links

Os links deverão:

- ser identificáveis visualmente;
- possuir descrição clara;
- indicar quando abrem nova aba.

---

# Formulários

Todo campo deverá possuir:

- Label associado;
- descrição quando necessário;
- mensagem de erro acessível;
- indicação de obrigatoriedade.

---

# Mensagens de Erro

As mensagens deverão:

- explicar o problema;
- indicar como corrigir;
- estar associadas ao campo correspondente.

---

# Feedback

Operações importantes deverão gerar feedback visual e, quando aplicável, serem anunciadas para tecnologias assistivas.

Exemplos:

- cadastro realizado;
- exclusão concluída;
- erro de conexão.

---

# Imagens

Toda imagem informativa deverá possuir texto alternativo.

Imagens decorativas deverão ser ignoradas por leitores de tela.

---

# Ícones

Ícones isolados deverão possuir descrição acessível.

---

# Modais

Os modais deverão:

- capturar o foco ao abrir;
- devolver o foco ao fechar;
- impedir interação com o fundo.

---

# Tabelas

Sempre que utilizadas deverão conter:

- cabeçalhos;
- descrição;
- estrutura semântica.

---

# Responsividade

A interface deverá manter acessibilidade em:

- Desktop
- Tablet
- Mobile

---

# Animações

Usuários com preferência por redução de movimento deverão ter animações reduzidas.

---

# Estados

Todo componente deverá prever:

- Focus
- Hover
- Active
- Disabled
- Error

---

# Leitores de Tela

A aplicação deverá utilizar HTML semântico.

Exemplos:

- header
- nav
- main
- section
- article
- footer

---

# Testes

A acessibilidade deverá ser validada através de:

- navegação por teclado;
- Lighthouse;
- leitores de tela;
- contraste de cores;
- testes manuais.

---

# Evolução

Todas as novas funcionalidades deverão seguir estas diretrizes desde sua concepção.
