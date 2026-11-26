# MERN Product Store

A full-stack product management app built with **MongoDB, Express, React and Node.js**, following the freeCodeCamp MERN tutorial (with additional guidance from the AsAProgrammer YouTube channel). Users can add, view, edit and delete products.

## Features

- REST API for product CRUD
- React frontend with Chakra UI, light/dark mode and client-side routing
- Global state handled with Zustand
- Single-server production mode: Express serves the built frontend

## Tech stack

| Layer | Tools |
| --- | --- |
| Frontend | React 19, Vite, Chakra UI, React Router, Zustand |
| Backend | Node.js, Express, Mongoose |
| Database | MongoDB |

## Getting started

### Prerequisites

Node.js 18+ and a MongoDB connection string (local or MongoDB Atlas).

### Setup

```bash
npm install
npm install --prefix frontend
```

Create a `.env` file in the project root:

```
MONGO_URI=mongodb+srv://<user>:<password>@<cluster>/<db>
PORT=5000
```

### Run in development

```bash
npm run dev                  # API on http://localhost:5000
npm run dev --prefix frontend  # Vite dev server (in a second terminal)
```

### Build and run for production

```bash
npm run build
npm start
```

In production the Express server serves `frontend/dist` and handles the API from one origin.

## API

Base path: `/api/products`

| Method | Path | Description |
| --- | --- | --- |
| `GET` | `/` | List all products |
| `POST` | `/` | Create a product (`name`, `price`, `image`) |
| `PUT` | `/:id` | Update a product |
| `DELETE` | `/:id` | Delete a product |

## Project structure

```
.
├── backend/
│   ├── config/db.js          # Mongo connection
│   ├── controllers/          # product handlers
│   ├── models/               # Mongoose schema
│   ├── routes/               # Express routes
│   └── server.js
└── frontend/
    └── src/
        ├── components/       # Navbar, ProductCard
        ├── pages/            # HomePage, CreatePage
        └── store/product.js  # Zustand store
```

## Credits

Based on the freeCodeCamp MERN course. This repo is my own practice implementation.
