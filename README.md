# 🌐 Nadia — Node.js MVC Web Application

[![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)](https://expressjs.com)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://postgresql.org)
[![Knex.js](https://img.shields.io/badge/Knex.js-E16426?style=flat-square)](https://knexjs.org)
[![EJS](https://img.shields.io/badge/EJS-A91E50?style=flat-square)](https://ejs.co)

A clean **Node.js MVC web application** built with **Express**, **Knex.js** (SQL query builder), and **EJS** server-side templates — demonstrating structured backend development with migrations, routing, and separation of concerns.

## ✨ Features

- 🗂️ **MVC architecture** — Models, Views, Controllers cleanly separated
- 🛤️ **Express routing** — modular route files per resource
- 🗄️ **Database migrations** — Knex.js schema migrations for version-controlled schema changes
- 🖥️ **Server-side rendering** — EJS templating with layouts and partials
- 🔐 **Session management** — Express sessions with secure cookie handling
- ✅ **Input validation** — server-side form validation with error messages
- 🌍 **Environment config** — `.env`-based configuration with `dotenv`

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Runtime | Node.js |
| Framework | Express.js |
| Database | PostgreSQL |
| Query Builder | Knex.js |
| Templating | EJS (Embedded JavaScript) |
| Sessions | express-session |
| Migrations | Knex migrations + seeds |
| Linting | ESLint + Prettier |

## 🏗️ Project Structure

```
nadia/
├── app.js                  # Express app setup, middleware, mount routes
├── bin/
│   └── www                 # HTTP server entry point
├── routes/
│   ├── index.js            # Home / public routes
│   └── [resource].js       # Resource-specific route files
├── lib/
│   ├── models/             # Knex-powered data access layer
│   └── helpers/            # Utility functions
├── views/
│   ├── layout/             # Base templates (header, footer)
│   ├── partials/           # Reusable EJS partials
│   └── [resource]/         # View files per resource
├── public/
│   ├── css/                # Stylesheets
│   ├── js/                 # Client-side scripts
│   └── images/
├── migrations/             # Knex database migrations (version-controlled schema)
├── knexfile.js             # Knex configuration (dev/test/prod)
├── .eslintrc.js
└── package.json
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- PostgreSQL running locally

```bash
git clone https://github.com/joshivignesh/nadia.git
cd nadia
npm install
```

### Environment setup

```bash
cp .env.example .env
```

```env
NODE_ENV=development
PORT=3000
DATABASE_URL=postgresql://user:password@localhost:5432/nadia_dev
SESSION_SECRET=your-secret-key
```

### Database setup

```bash
# Run all migrations
npx knex migrate:latest

# Seed the database with sample data
npx knex seed:run
```

### Run

```bash
# Development (with nodemon)
npm run dev

# Production
npm start
```

App available at `http://localhost:3000`

## 🗄️ Database Migrations

Migrations live in `/migrations` — each is a timestamped file that defines `up()` (apply) and `down()` (rollback):

```bash
# Create a new migration
npx knex migrate:make create_users_table

# Run pending migrations
npx knex migrate:latest

# Rollback last batch
npx knex migrate:rollback
```

## 💡 Key Patterns

- **Knex query builder** — type-safe, composable SQL without a full ORM
- **MVC separation** — routes delegate to controllers, controllers use models
- **Migration-first schema** — schema changes are code-reviewed and reversible
- **EJS layouts** — base template with `<%- body %>` injection for consistent UI

## 👤 Author

**Vignesh Joshi** — Senior Full Stack Engineer  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-joshivignesh-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/joshivignesh)
[![GitHub](https://img.shields.io/badge/GitHub-joshivignesh-181717?style=flat-square&logo=github)](https://github.com/joshivignesh)
