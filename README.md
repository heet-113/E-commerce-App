# E-Commerce Platform

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

## Deployment

### Render backend

- Root directory: `backend`
- Build command: `npm ci`
- Start command: `npm start`
- Required env vars:
  - `MONGODB_URI`
  - `JWT_SECRET`
  - `CORS_ORIGIN` should be your GitHub Pages URL

### GitHub Pages frontend

- Set `VITE_API_URL` to `https://e-commerce-backend-rl2u.onrender.com/api` during build
- Configure GitHub Pages to deploy from GitHub Actions so it serves the uploaded `frontend/dist` artifact
- In the frontend repo settings, set Pages source to GitHub Actions
- The included GitHub Actions workflow builds the frontend and deploys it directly through the Pages API
- If you use a custom Pages path, keep the Vite base path relative

## API

- `GET /api/health`
- `POST /api/auth/login`
- `GET /api/auth/me`
- `GET /api/products`
- `POST /api/products` (admin)
- `PUT /api/products/:id` (admin)
- `DELETE /api/products/:id` (admin)
- `GET /api/orders`
- `POST /api/orders`
- `PATCH /api/orders/:id/status` (admin)
