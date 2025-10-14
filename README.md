# Alura Books

Alura Books is a React single-page application that lets readers discover new titles, search the catalogue, and manage a personal list of favourites. The interface was built during the Alura React course and showcases common front-end patterns such as reusable components, client-side routing, and integration with a REST API.

## Features

- **Curated highlights** – Home page with a hero search section and a carousel of the latest releases.
- **Smart search** – Search suggestions are populated from the `/livros` endpoint and allow adding a title to the favourites list with a single click.
- **Favourite management** – Dedicated page that loads data from the `/favoritos` endpoint and lets users remove a book from their saved list.
- **Reusable design system** – Components such as the header, logo, buttons, cards, and typography were implemented with `styled-components` to encourage reuse and easy theme updates.

## Project structure

```
src/
├─ componentes/        # Reusable UI building blocks (header, search box, cards, etc.)
├─ rotas/              # Route-level pages (Home and Favoritos)
├─ servico(s)/         # API clients responsible for livros and favoritos endpoints
├─ imagens/            # Static assets used by the UI
├─ index.js            # React entry point with router and global styles
└─ reportWebVitals.js  # CRA performance helper
```

> **Note:** The project currently exposes both `src/servico` and `src/servicos`. They contain equivalent Axios clients. Keep one or consolidate them before adding new features to avoid duplication.

## Getting started

### Prerequisites

- [Node.js](https://nodejs.org/) v16 or later
- npm (bundled with Node.js)
- A REST service serving the following endpoints on `http://localhost:8000`:
  - `GET /livros` – returns the catalogue used by the search and highlights
  - `GET /favoritos`, `POST /favoritos/:id`, `DELETE /favoritos/:id` – manages the favourites list

During the original course a [json-server](https://github.com/typicode/json-server) instance was used to mock these endpoints. Any equivalent implementation will work.

### Installation

```bash
# install dependencies
npm install
```

### Useful scripts

```bash
# start the development server on http://localhost:3000
npm start

# run the Jest test suite in watch mode
npm test

# generate an optimized production build in the build/ directory
npm run build
```

## Development notes

- Components rely on `styled-components`. Ensure your editor supports tagged template literals for the best DX.
- API calls are implemented with Axios. To extend the API client, add new helpers to the `servico` directory and export them alongside the existing ones.
- The app uses React Router v6. Add new pages by defining routes in `src/index.js` and creating a corresponding component in `src/rotas`.

## License

This project is provided for educational purposes as part of the Alura React learning path. Please review the course terms of use before distributing or deploying the application.
