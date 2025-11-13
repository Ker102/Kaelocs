# Kaelocs Next.js Application

[![CodeQL status](https://img.shields.io/github/actions/workflow/status/Kaelocs/Kaelocs/codeql.yml?label=CodeQL&logo=github)](https://github.com/Kaelocs/Kaelocs/actions/workflows/codeql.yml)
[![Dependabot](https://img.shields.io/badge/Dependabot-enabled-025E8C?logo=dependabot)](https://github.com/Kaelocs/Kaelocs/network/updates)
[![License: MIT](https://img.shields.io/github/license/Kaelocs/Kaelocs)](./LICENSE)
[![Open issues](https://img.shields.io/github/issues/Kaelocs/Kaelocs?logo=github)](https://github.com/Kaelocs/Kaelocs/issues)
[![Contributors](https://img.shields.io/github/contributors/Kaelocs/Kaelocs?logo=github)](https://github.com/Kaelocs/Kaelocs/graphs/contributors)

A modern Next.js application with TypeScript, Tailwind CSS, dependable CI/CD, and essential libraries for building production-ready web applications.

## Features

- ⚡ **Next.js 15** with App Router and Turbopack
- 🎨 **Tailwind CSS 4** for styling
- 📘 **TypeScript** for type safety
- 🔐 **NextAuth.js** with Google OAuth for user authentication
- 🤖 **Google Gemini 2.5 Flash** AI integration
- 🛡️ **Dual Authentication System** - User & Admin layers
- 🧪 **Vitest** with React Testing Library for testing
- 🎯 **ESLint** and **Prettier** for code quality
- 🔄 **React Query** for server state management
- 🎭 **Zustand** for client state management
- 📝 **React Hook Form** with Zod validation
- 🌙 **next-themes** for dark mode support
- 🎨 **Lucide React** for beautiful icons

## Getting Started

### Prerequisites

- Node.js 18.19.1 or later
- npm 9.2.0 or later

### Installation

1. Install dependencies:

```bash
npm install
```

2. Set up environment variables:

Copy the `env.template` file to `.env.local`:

```bash
cp env.template .env.local
```

Then edit `.env.local` and fill in your credentials:
- **Google OAuth**: Follow the [Google Auth Setup Guide](./GOOGLE_AUTH_SETUP.md)
- **Admin Password**: Set a secure password for admin access
- **Google AI API Key**: Get from [Google AI Studio](https://makersuite.google.com/app/apikey)

For detailed Google OAuth setup instructions, see [GOOGLE_AUTH_SETUP.md](./GOOGLE_AUTH_SETUP.md)

### Development

Run the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Build

Build the application for production:

```bash
npm run build
```

### Start Production Server

```bash
npm start
```

## Available Scripts

- `npm run dev` - Start development server with Turbopack
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run lint` - Run ESLint
- `npm run format` - Format code with Prettier
- `npm run format:check` - Check code formatting
- `npm test` - Run tests with Vitest
- `npm run test:ui` - Run tests with UI
- `npm run test:coverage` - Run tests with coverage

## Authentication System

This application uses a **dual authentication system**:

### 1. User Authentication (Google OAuth)
- **Purpose**: Save user progress and chat history across sessions
- **Provider**: Google OAuth via NextAuth.js
- **Access Level**: Anyone with a Google account can sign in
- **Features**:
  - Persistent user sessions
  - Chat history saved per user
  - Profile management

### 2. Admin Authentication (Password-based)
- **Purpose**: Gate access to AI/LLM features
- **Method**: Password authentication via Zustand store
- **Access Level**: Only users with admin credentials
- **Features**:
  - Required to use Gemini AI chat features
  - Independent of user authentication
  - Session-based access control

**How it works:**
- Users can sign in with Google to save their progress
- To actually use the AI features, they must also authenticate as admin
- Both authentications work independently and serve different purposes

## Project Structure

```
├── app/                      # Next.js app directory
│   ├── api/
│   │   ├── auth/            # NextAuth API routes
│   │   └── chat/            # AI chat API endpoint
│   ├── auth/
│   │   └── signin/          # Custom sign-in page
│   ├── admin/
│   │   └── login/           # Admin login page
│   ├── layout.tsx           # Root layout
│   ├── page.tsx             # Home page
│   └── globals.css          # Global styles
├── components/              # React components
│   ├── ui/                  # UI components
│   ├── Chat.tsx             # Main chat component
│   ├── DarkVeil.tsx         # Animated background
│   └── providers.tsx        # App providers
├── lib/                     # Utility functions
│   ├── auth-store.ts        # Admin auth state
│   ├── brave-search.ts      # Web search integration
│   ├── web-fetcher.ts       # Web content fetcher
│   ├── utils.ts             # Helper utilities
│   └── constants.ts         # App constants
├── types/                   # TypeScript types
│   ├── index.ts             # Common types
│   └── next-auth.d.ts       # NextAuth type extensions
├── hooks/                   # Custom React hooks
├── test/                    # Test setup and utilities
└── public/                  # Static files
```

## Technologies

### Core
- [Next.js](https://nextjs.org/) - React framework
- [React](https://react.dev/) - UI library
- [TypeScript](https://www.typescriptlang.org/) - Type safety
- [NextAuth.js](https://next-auth.js.org/) - Authentication for Next.js

### Styling
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS
- [class-variance-authority](https://cva.style/) - Component variants
- [clsx](https://github.com/lukeed/clsx) - Class names utility
- [tailwind-merge](https://github.com/dcastil/tailwind-merge) - Merge Tailwind classes

### State Management & Data Fetching
- [Zustand](https://zustand-demo.pmnd.rs/) - State management
- [React Query](https://tanstack.com/query) - Server state management
- [Axios](https://axios-http.com/) - HTTP client

### Forms & Validation
- [React Hook Form](https://react-hook-form.com/) - Form handling
- [Zod](https://zod.dev/) - Schema validation

### UI & Icons
- [Lucide React](https://lucide.dev/) - Icons
- [next-themes](https://github.com/pacocoursey/next-themes) - Theme management

### Testing
- [Vitest](https://vitest.dev/) - Test runner
- [React Testing Library](https://testing-library.com/react) - Component testing

### Code Quality
- [ESLint](https://eslint.org/) - Linting
- [Prettier](https://prettier.io/) - Code formatting

## Security & Maintenance

- ✅ Automated dependency updates powered by [Dependabot](https://github.com/Kaelocs/Kaelocs/network/updates)
- ✅ Continuous [CodeQL](https://codeql.github.com/) scanning via GitHub Actions to catch security and quality regressions
- ✅ [Security policy](./SECURITY.md) describing how to report vulnerabilities

## Community & Support

- Read the [Code of Conduct](./CODE_OF_CONDUCT.md) to understand our expectations
- Learn how to contribute in [CONTRIBUTING.md](./CONTRIBUTING.md) and get help in [SUPPORT.md](./SUPPORT.md)
- Use the curated GitHub issue and PR templates so we can triage faster

## License

MIT
