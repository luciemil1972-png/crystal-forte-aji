# Crystal Forte Web3 Platform

This project contains:
- a React frontend in `public-site/`
- an Express backend in `backend/`

## Local development

### 1) Install backend dependencies

cd backend
npm install

### 2) Install frontend dependencies

cd ../public-site
npm install

### 3) Create environment file

Copy `.env.example` to `.env` in the project root, then set your values.

### 4) Start backend

cd backend
npm run dev

### 5) Start frontend

cd public-site
npm run dev

The frontend should use `VITE_API_BASE_URL` to point at the backend server.

## Production deployment

### Frontend
Deploy the contents of `public-site/` to a static host such as:
- Vercel
- Netlify
- Cloudflare Pages
- Azure Static Web Apps

Set this environment variable:
- `VITE_API_BASE_URL=https://api.yourdomain.com`

### Backend
Deploy `backend/` to a Node server such as:
- Render
- Railway
- Fly.io
- Azure App Service
- DigitalOcean App Platform

Set these environment variables:
- `PORT=5000`
- `FRONTEND_URL=https://yourdomain.com`
- `JWT_SECRET=<secure-random-secret>`
- `ADMIN_EMAIL=<admin@example.com>`
- `ADMIN_PASSWORD=<strong-password>`
- `ADMIN_WALLET=<real-wallet-address>`

### Public API access
The browser must be able to reach the API over HTTPS. Configure CORS so the frontend domain is allowed.

### Admin access
Use the admin login endpoint to obtain a JWT:
- `POST /api/auth/admin/login`

Then send the returned token in the `Authorization: Bearer <token>` header.

### Crypto wallet flow
This app expects a wallet provider such as MetaMask to be available in the browser. For real crypto deposits, you will also need:
- a real wallet address controlled by your platform
- blockchain monitoring for incoming transfers
- transaction validation and secure key handling
- deployment of the backend on a trusted host
