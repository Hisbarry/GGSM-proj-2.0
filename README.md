# GGSM Web Project - Full Stack Application

A modern full-stack website for Gods Grace Salvation Ministries built with React + Tailwind CSS (frontend) and NestJS + PostgreSQL + Prisma (backend).

## Project Structure

```
├── frontend/                 # React + Tailwind CSS application
│   ├── src/
│   │   ├── components/       # Reusable React components
│   │   ├── pages/            # Page components
│   │   ├── App.tsx           # Main app component
│   │   └── main.tsx          # Entry point
│   ├── package.json
│   ├── vite.config.ts
│   ├── tailwind.config.js
│   └── tsconfig.json
├── backend/                  # NestJS API server
│   ├── src/
│   │   ├── modules/          # Feature modules
│   │   │   └── contact/      # Contact form module
│   │   ├── prisma/           # Prisma service
│   │   ├── main.ts           # Entry point
│   │   └── app.module.ts     # Root module
│   ├── prisma/
│   │   ├── schema.prisma     # Database schema
│   │   └── seed.js           # Database seeding
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
└── .github/
    └── copilot-instructions.md
```

## Tech Stack

### Frontend
- **Framework**: React 18
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **Routing**: React Router v6
- **HTTP Client**: Axios
- **Language**: TypeScript

### Backend
- **Framework**: NestJS
- **Runtime**: Node.js
- **Database**: PostgreSQL
- **ORM**: Prisma
- **Validation**: class-validator
- **Language**: TypeScript

## Getting Started

### Prerequisites
- Node.js v18+ 
- PostgreSQL 12+
- npm or yarn

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on `http://localhost:5173`

### Backend Setup

1. **Setup Database**
```bash
cd backend
cp .env.example .env
# Edit .env and add your PostgreSQL connection string
```

2. **Install dependencies**
```bash
npm install
```

3. **Setup Prisma**
```bash
npm run db:generate
npm run db:migrate
npm run db:seed
```

4. **Start server**
```bash
npm run start:dev
```

Backend runs on `http://localhost:3000`

## Available Scripts

### Frontend
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

### Backend
- `npm run start:dev` - Start development server with hot reload
- `npm run build` - Build TypeScript
- `npm run start:prod` - Start production build
- `npm run lint` - Run ESLint
- `npm run test` - Run tests
- `npm run db:migrate` - Run Prisma migrations
- `npm run db:seed` - Seed database

## API Endpoints

### Contact Module
- `POST /api/contact/send` - Submit contact form
- `GET /api/contact` - Get all contacts (admin)
- `GET /api/contact/:id` - Get specific contact (admin)

## Environment Variables

### Backend (.env)
```
DATABASE_URL=postgresql://user:password@localhost:5432/ggsm_db
PORT=3000
NODE_ENV=development
```

### Frontend (.env)
```
VITE_API_URL=http://localhost:3000/api
```

## Database Schema

### Contact Table
- id (String, CUID primary key)
- name (String)
- email (String)
- message (Text)
- createdAt (DateTime)
- updatedAt (DateTime)

### Post Table (for blog)
- id (String, CUID primary key)
- title (String)
- content (Text)
- published (Boolean)
- createdAt (DateTime)
- updatedAt (DateTime)

### User Table
- id (String, CUID primary key)
- email (String, unique)
- name (String, optional)
- role (String, default: "user")

## Features

### Frontend
- ✅ Responsive design with Tailwind CSS
- ✅ React Router for navigation
- ✅ Contact form with validation
- ✅ Modern UI with smooth animations
- ✅ TypeScript support

### Backend
- ✅ RESTful API with NestJS
- ✅ PostgreSQL with Prisma ORM
- ✅ Input validation
- ✅ Error handling
- ✅ CORS enabled

## Development Workflow

1. Start PostgreSQL server
2. Run backend: `cd backend && npm run start:dev`
3. Run frontend: `cd frontend && npm run dev`
4. Open browser to `http://localhost:5173`

## Project Pages

- **Home** - Hero section with weekly activities
- **About** - Information about the ministry
- **Blog** - Latest updates and posts
- **Contact** - Contact form with backend integration

## Future Enhancements

- Authentication & Authorization
- Blog management system
- Admin dashboard
- Email notifications
- Image optimization
- Progressive Web App (PWA)
- API documentation (Swagger/OpenAPI)

## Contributing

Please maintain the following conventions:
- Use TypeScript for type safety
- Follow NestJS module structure in backend
- Use Tailwind CSS utility classes in frontend
- Keep components small and reusable
- Add proper error handling

## Support

Contact GGSM IT DEPARTMENT for support

## License

MIT
