# TradeBoost.AI - Trading Education Platform

## Overview

TradeBoost.AI is a modern web application designed to help users learn trading strategies and improve their trading skills. The platform features a React-based frontend with shadcn/ui components and an Express.js backend, using PostgreSQL for data persistence through Drizzle ORM.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state
- **UI Components**: shadcn/ui component library with Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **Build Tool**: Vite for development and bundling

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ESM modules
- **Database ORM**: Drizzle ORM for type-safe database operations
- **API Pattern**: RESTful API with `/api` prefix
- **Session Management**: Built-in session handling with PostgreSQL store

### Database Design
- **Database**: PostgreSQL (configured for Neon serverless)
- **Schema Management**: Drizzle Kit for migrations
- **Current Schema**: Users table with username/password authentication
- **Location**: `shared/schema.ts` for cross-platform type sharing

## Key Components

### Frontend Structure
- `client/src/App.tsx` - Main application with routing setup
- `client/src/pages/` - Page components (splash, welcome, not-found)
- `client/src/components/ui/` - Reusable UI components from shadcn/ui
- `client/src/lib/` - Utility functions and query client configuration
- `client/src/hooks/` - Custom React hooks

### Backend Structure
- `server/index.ts` - Express server setup with middleware
- `server/routes.ts` - API route definitions (currently empty, ready for implementation)
- `server/storage.ts` - Data access layer with memory storage fallback
- `server/vite.ts` - Development server integration with Vite HMR

### Shared Code
- `shared/schema.ts` - Database schema definitions and TypeScript types
- Type-safe data models shared between frontend and backend

## Data Flow

1. **Frontend Requests**: React components use TanStack Query for API calls
2. **API Layer**: Express.js handles requests with `/api` prefix
3. **Data Access**: Storage interface abstracts database operations
4. **Database**: PostgreSQL with Drizzle ORM for type-safe queries
5. **Response**: JSON responses with error handling middleware

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless** - PostgreSQL serverless connection
- **drizzle-orm** & **drizzle-kit** - Database ORM and migration tools
- **express** - Web framework
- **react** & **react-dom** - Frontend framework
- **@tanstack/react-query** - Server state management
- **wouter** - Lightweight routing
- **tailwindcss** - CSS framework

### UI Dependencies
- **@radix-ui/react-*** - Headless UI components
- **lucide-react** - Icon library
- **class-variance-authority** - CSS class management
- **clsx** & **tailwind-merge** - Utility libraries

## Deployment Strategy

### Development
- **Frontend**: Vite dev server with HMR
- **Backend**: tsx for TypeScript execution
- **Database**: Drizzle push for schema updates
- **Environment**: NODE_ENV=development

### Production
- **Build Process**: 
  1. Frontend: Vite builds to `dist/public`
  2. Backend: esbuild bundles to `dist/index.js`
- **Deployment**: Single Node.js server serving both frontend and API
- **Database**: PostgreSQL with connection pooling
- **Environment**: NODE_ENV=production

### Key Features
- **Hot Module Replacement**: Full-stack development with live reloading
- **Type Safety**: End-to-end TypeScript with shared types
- **Modern Tooling**: Latest versions of React, Node.js, and build tools
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Error Handling**: Comprehensive error boundaries and API error handling

## Recent Changes

### July 10, 2025
- **Home Screen Implementation**: Added comprehensive home screen with hamburger menu sidebar
- **Theme System**: Implemented light/dark theme toggle with global theme switching
- **Sidebar Menu**: Added professional sidebar with navigation items, theme toggle, and privacy links
- **Hero Banner**: Integrated custom trading banner image with overlay text
- **Authentication Flow**: Complete login/signup screens with navigation to home screen
- **5-Tab Bottom Navigation**: Updated to include Home, Learn, Trade, Portfolio, AI tabs
- **Notification System**: Added notification bell icon with dedicated notifications screen
- **Enhanced AI Tools Section**: 5 specialized AI tools (Ask AI, Chart Analysis, Indicators, Screener, Price Alerts)
- **Floating Ask AI Button**: Added floating action button for quick AI access
- **Responsive Design**: Optimized for mobile-first experience with proper spacing
- **Learn Hub Integration**: Embedded complete Learn Hub functionality into home screen's Learn tab
- **Wallet Screen**: Created comprehensive wallet with balance tracking, transaction history, and insights
- **Profile Screen**: Added detailed profile management with user stats, achievements, and account settings
- **Leaderboard Screen**: Built competitive leaderboard with ₹10,000 weekly bonus for #1 rank, animations, and detailed rankings
- **Virtual Trading Screen**: Created comprehensive trading platform with stock search, buy/sell functionality, portfolio tracking, and AI tips
- **Portfolio Screen**: Built deep analytical portfolio view with holdings breakdown, sector allocation charts, AI insights, and performance tracking

## Current Features

The application now includes:
- **Splash Screen**: Loading animation that transitions to welcome page
- **Welcome Screen**: Showcases platform's core features (Learn, Practice, Grow)
- **Authentication**: Login and signup screens with form validation
- **Home Screen**: Main dashboard with hero banner, feature cards, and bottom navigation
- **Sidebar Navigation**: Hamburger menu with theme toggle and comprehensive navigation
- **Theme System**: Light/dark mode with persistent user preference
- **AI Tools**: Dedicated section with 5 AI-powered trading tools