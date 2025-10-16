# Estante Digital

Estante Digital é uma single-page application em React que ajuda leitoras e leitores a descobrir novos títulos, pesquisar o catálogo e administrar uma lista pessoal de favoritos. O projeto foi desenvolvido durante o curso de React da Alura e serve como vitrine para padrões modernos de front-end, incluindo componentes reutilizáveis, roteamento no cliente e consumo de uma API REST.

## Funcionalidades

- **Destaques editoriais** – A página inicial combina uma busca em destaque com um carrossel dos lançamentos mais recentes.
- **Busca inteligente** – As sugestões são preenchidas com dados do endpoint `/livros`, permitindo adicionar um título aos favoritos com um clique.
- **Gestão de favoritos** – A página dedicada carrega dados de `/favoritos` e possibilita remover livros já salvos.
- **Design system reutilizável** – Header, logo, botões, cards e tipografia foram implementados com `styled-components`, facilitando a manutenção do tema.

## Estrutura do projeto

```
src/
├─ componentes/        # Blocos de UI reutilizáveis (cabeçalho, campo de busca, cards etc.)
├─ rotas/              # Páginas de alto nível (Home e Favoritos)
├─ servico(s)/         # Clientes de API responsáveis pelos endpoints de livros e favoritos
├─ imagens/            # Ativos estáticos usados na interface
├─ index.js            # Ponto de entrada do React com router e estilos globais
└─ reportWebVitals.js  # Utilitário do Create React App para métricas de performance
```

> **Atenção:** O projeto mantém as pastas `src/servico` e `src/servicos`, que contêm clientes Axios equivalentes. Considere consolidá-las antes de evoluir a integração para evitar duplicidade.

## Pré-requisitos

- [Node.js](https://nodejs.org/) versão 16 ou superior
- npm (instalado junto com o Node.js)
- Uma API REST disponível em `http://localhost:8000` com os endpoints:
  - `GET /livros` – catálogo utilizado na busca e nos destaques
  - `GET /favoritos`, `POST /favoritos/:id`, `DELETE /favoritos/:id` – operações da lista de favoritos

Durante o curso original utilizou-se um [json-server](https://github.com/typicode/json-server) para simular esses endpoints, mas qualquer implementação equivalente funciona.

## Como executar

```bash
# instalar dependências
npm install

# iniciar o servidor de desenvolvimento em http://localhost:3000
npm start
```

## Scripts disponíveis

```bash
# executar os testes (Jest) em modo watch
npm test

# gerar build otimizado na pasta build/
npm run build
```

## Notas de desenvolvimento

- Os componentes utilizam `styled-components`. Configure seu editor para dar suporte a tagged template literals e obter a melhor experiência.
- As chamadas HTTP são feitas com Axios. Novas integrações podem ser adicionadas no diretório `servico`, exportando-as junto com os helpers existentes.
- O projeto usa React Router v6. Para adicionar novas páginas, defina as rotas em `src/index.js` e crie o componente correspondente em `src/rotas`.

## Licença

Este material é disponibilizado para fins educacionais como parte da trilha de React da Alura. Consulte os termos do curso antes de redistribuir ou publicar a aplicação.
