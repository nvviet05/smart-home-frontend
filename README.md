# Smart Home Frontend

Web interface for the Smart Home system — monitor sensors and control devices remotely via the browser.

## Tech Stack

| Layer        | Technology               |
| ------------ | ------------------------ |
| Framework    | React 19                 |
| Build tool   | Vite 6                   |
| Routing      | React Router DOM 7       |
| HTTP Client  | Axios                    |
| Linting      | ESLint 9                 |
| Formatting   | Prettier                 |

## Getting Started

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/smart-home-frontend.git
cd smart-home-frontend

# 2. Install dependencies
npm install

# 3. Create .env file from the template
cp .env.example .env
# Update the values in .env if needed

# 4. Run the dev server
npm run dev
```

Open your browser at `http://localhost:5173`

## Environment Variables

See `.env.example`:

| Variable             | Description                     | Default                  |
| -------------------- | ------------------------------- | ------------------------ |
| `VITE_API_BASE_URL`  | Backend API URL                 | `http://localhost:5000`  |
| `VITE_APP_TITLE`     | Application title (optional)    | `Smart Home`             |

## Scripts

| Command           | Description                           |
| ----------------- | ------------------------------------- |
| `npm run dev`     | Run dev server (HMR)                  |
| `npm run build`   | Build for production into `dist/`     |
| `npm run preview` | Preview the production build          |
| `npm run lint`    | Check for ESLint errors               |
| `npm run lint:fix`| Auto-fix ESLint errors                |
| `npm run format`  | Format code with Prettier             |

## Project Structure

```
src/
├── api/               # Axios instance & API services
│   ├── axios.js        # Axios config (interceptors, base URL)
│   └── index.js        # Export API modules
├── assets/             # Images, fonts, static files
├── components/         # Shared components (Button, Card, Modal...)
│   └── layout/         # Layout components (Navbar, Sidebar)
├── contexts/           # React Context providers (Auth, Theme...)
├── hooks/              # Custom hooks (useAuth, useDevices...)
├── pages/              # Main pages
│   ├── Login.jsx       # Login
│   ├── Dashboard.jsx   # System overview
│   ├── Devices.jsx     # Device management
│   ├── Sensors.jsx     # Sensor data
│   └── NotFound.jsx    # 404 page
├── routes/             # Routing configuration
│   └── AppRouter.jsx
├── utils/              # Utility functions
├── App.jsx             # Root component
├── App.css
├── main.jsx            # Entry point
└── index.css
```

## Main Screens

1. **Login** — Sign in / register an account
2. **Dashboard** — Overview: device status, sensor charts
3. **Devices** — Device list, toggle on/off, add/remove
4. **Sensors** — Temperature, humidity, and light charts over time
5. **404** — Page not found

## Branch Strategy

| Branch           | Purpose                                     |
| ---------------- | ------------------------------------------- |
| `main`           | Stable — only merge when code is stable     |
| `develop`        | Integration — merge features here first     |
| `feature/*`      | Feature branches (e.g. `feature/auth-api`)  |
| `fix/*`          | Bug fix branches (e.g. `fix/login-bug`)     |

**Conventions:**
- Do not push directly to `main`
- Work on separate branches → merge into `develop` → when stable → merge into `main`
- Create a Pull Request for review before merging

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
