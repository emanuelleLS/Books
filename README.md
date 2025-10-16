# 📚 Alura Books

**Alura Books** é uma aplicação *single-page* desenvolvida em **React**, que permite aos leitores descobrir novos títulos, pesquisar no catálogo e gerenciar uma lista pessoal de favoritos.  
O projeto foi criado durante o curso de React da **Alura** e demonstra padrões comuns de front-end, como componentes reutilizáveis, *client-side routing* e integração com uma **API REST**.

---

## ✨ Funcionalidades

- **Destaques selecionados** – Página inicial com uma seção de busca principal e um carrossel dos lançamentos mais recentes.  
- **Busca inteligente** – Sugestões de pesquisa obtidas do endpoint `/livros`, permitindo adicionar um livro aos favoritos com um clique.  
- **Gerenciamento de favoritos** – Página dedicada que consome os dados do endpoint `/favoritos` e permite remover livros da lista.  
- **Design system reutilizável** – Componentes como cabeçalho, logo, botões, cartões e tipografia criados com `styled-components`, promovendo reutilização e fácil personalização de temas.

---

## 🗂️ Estrutura do projeto

```
src/
├─ componentes/        # Componentes reutilizáveis (header, busca, cards, etc.)
├─ rotas/              # Páginas principais (Home e Favoritos)
├─ servico(s)/         # Clientes da API para os endpoints de livros e favoritos
├─ imagens/            # Recursos estáticos da interface
├─ index.js            # Ponto de entrada do React com roteamento e estilos globais
└─ reportWebVitals.js  # Utilitário do CRA para medir performance
```

> ⚠️ **Nota:** O projeto possui tanto `src/servico` quanto `src/servicos`.  
> Eles contêm implementações equivalentes usando Axios.  
> Mantenha apenas um deles para evitar duplicação de código.

---

## 🚀 Primeiros passos

### 🔧 Pré-requisitos

- [Node.js](https://nodejs.org/) v16 ou superior  
- npm (incluso com o Node.js)  
- Um serviço REST rodando em `http://localhost:8000` com os seguintes endpoints:
  - `GET /livros` – Retorna o catálogo de livros  
  - `GET /favoritos`, `POST /favoritos/:id`, `DELETE /favoritos/:id` – Gerencia a lista de favoritos  

Durante o curso original, foi usado o [json-server](https://github.com/typicode/json-server) para simular esses endpoints, mas qualquer API equivalente funcionará.

---

### ⚙️ Instalação

```bash
# Instalar dependências
npm install
```

---

### 🧠 Scripts úteis

```bash
# Iniciar o servidor de desenvolvimento (http://localhost:3000)
npm start

# Executar os testes com Jest em modo watch
npm test

# Gerar a build otimizada na pasta build/
npm run build
```

---

## 🧩 Notas de desenvolvimento

- Os componentes utilizam **styled-components** — verifique se seu editor tem suporte a *tagged template literals*.  
- As chamadas à API são feitas com **Axios**. Para estender o cliente, adicione novos *helpers* em `src/servico`.  
- O roteamento usa **React Router v6**. Adicione novas páginas em `src/rotas` e defina as rotas em `src/index.js`.

---

## 📄 Licença

Este projeto foi desenvolvido com fins **educacionais** como parte do curso de React da **Alura**.  
Consulte os **termos de uso** do curso antes de redistribuir ou implantar a aplicação.

---

### 🧠 Curiosidade

O nome *Alura Books* vem da proposta de criar uma experiência moderna de livraria digital, aplicando os conceitos aprendidos em React para construir uma aplicação funcional e modular.
