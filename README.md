# Meteora 🛍️

![Status](https://img.shields.io/badge/status-completed-green?style=for-the-badge)
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-4-646CFF?style=for-the-badge&logo=vite&logoColor=white)

A fashion e-commerce front-end built with React — product catalog, a shopping cart managed with Context API and a reducer, and routing between a home page and a cart page.

**Live demo:** [meteora-three-tau.vercel.app](https://meteora-three-tau.vercel.app)

---

## Overview

Meteora is the storefront side of a clothing shop: a home page with a carousel, categories, featured products and a newsletter block, plus a cart that opens either as a side panel or as a full page with an order summary. The page content is in Brazilian Portuguese, and product data comes from static JSON files, so there is no backend.

The cart is where most of the code is. It lives in one context provider, updated through a reducer with three actions (add, remove, change quantity), and every component reads and changes it through a single custom hook. Item count and total are derived from the cart array, so the navbar badge, the side panel and the summary always agree.

---

## Architecture

```
meteora/
├── index.html                       # Bootstrap (CDN), fonts, root element
├── vite.config.js                   # React plugin and the "@" alias for src/
└── src/
    ├── main.jsx                     # Entry point
    ├── App.jsx                      # Router and cart provider
    ├── pages/                       # Home, Carrinho, PaginaErro (404)
    ├── components/                  # About 30 components, one folder each
    │   ├── BarraNavegacao/          # Responsive navbar, search field, cart button
    │   ├── Carrossel/               # Home carousel
    │   ├── Produtos/                # Product grid and product card
    │   ├── CarrinhoSuspenso/        # Side panel cart
    │   ├── ItemCarrinho/            # Cart line item with quantity controls
    │   ├── Sumario/                 # Order summary
    │   └── ...                      # Categories, perks, newsletter, footer, shared UI
    ├── context/CarrinhoContext.jsx  # Cart state provider
    ├── reducers/carrinhoReducer.jsx # ADD_PRODUTO, REMOVE_PRODUTO, UPDATE_QUANTIDADE
    ├── hooks/useCarrinhoContext.jsx # Cart actions exposed to components
    ├── utils/formatadorMoeda.js     # BRL currency formatting
    └── mocks/                       # Static JSON: products, categories, perks, slides
```

### Concepts Applied

| Concept | How it shows up |
|---|---|
| **State management** | `useReducer` inside a Context provider; the reducer handles adding a product, removing it, and updating its quantity |
| **Custom hook** | `useCarrinhoContext` wraps `dispatch` in `adicionarProduto`, `removerProduto` (decrements, and removes the item at quantity 1) and `removerProdutoCarrinho` |
| **Derived data** | Item count and total price computed with `useMemo` from the cart array |
| **Routing** | React Router v6: `/` for home, `/carrinho` for the cart page, `*` for a 404 page |
| **Reusable components** | One `Botao` component with a variant map supplies the button styles used across the app |
| **Layout** | Bootstrap 5 grid, navbar, carousel and offcanvas, plus custom CSS in `App.css` |
| **Formatting** | `Intl.NumberFormat` with `pt-BR` locale and BRL currency |

---

## Features

- Home page with a three-slide carousel, six categories, six featured products, a perks section and a newsletter block
- Add products to the cart from the product cards
- Increase, decrease or delete items from the cart, with quantity updated live
- Cart available as a side panel from the navbar and as its own page with an order summary
- Navbar that collapses on small screens, with the cart button placed differently per breakpoint
- 404 page for unknown routes

---

## Technologies

- **React 18**
- **Vite 4**
- **React Router 6**
- **Bootstrap 5.3** — loaded from a CDN
- **Context API and `useReducer`**
- **Google Fonts** (Inter) and **Material Symbols** icons
- **Vercel** — deployment

---

## How to Run

**Prerequisites:** Node.js 16 or higher

```bash
git clone https://github.com/victorhubarb/meteora.git
cd meteora
npm install
npm run dev
```

Vite prints the local address, `http://localhost:5173` by default. To check a production build:

```bash
npm run build
npm run preview
```

---

## What I'd Improve Next

- **Persist the cart.** The cart starts empty on every reload because nothing is stored. Saving it to `localStorage` is the natural next step.
- **Connect the placeholder actions.** "Finalizar compra", the search field and the newsletter button have no behavior yet.
- **Replace the mock data.** Products live in `src/mocks`, which keeps data separate from components and makes swapping in an API straightforward.
- **Test the reducer and simplify the totals.** The reducer takes a state and an action, which makes it easy to unit test. The item count and total could also be derived directly in the provider instead of being copied into state by an effect.

---

## Author

**Victor Hugo Barbosa**
[GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
