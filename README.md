# E-Commerce Platform

[Live Demo](https://heet-113.github.io/E-commerce-frontend/)

A deployable full-stack e-commerce demo with:

- A React/Vite frontend for GitHub Pages
- An Express API backend for Render
- Login, role-based access, product management, cart, checkout, and order tracking
- MongoDB persistence for users, products, and orders

## Demo accounts

- Admin: `admin@shop.local` / `Admin123!`
- User: `customer@shop.local` / `User123!`

## Local development

### Backend

1. Set `backend/.env`:

```env
PORT=4000
MONGODB_URI=your-mongodb-connection-string
JWT_SECRET=replace-with-a-long-random-string
CORS_ORIGIN=http://localhost:5173
```

2. Install and run:

```bash
cd backend
npm install
npm start
```

### Frontend

1. Set `frontend/.env`:

```env
VITE_API_URL=http://localhost:4000
```

2. Install and run:

```bash
cd frontend
npm install
npm run dev
```