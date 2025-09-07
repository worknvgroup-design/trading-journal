# TradingJournal Pro

## Overview

TradingJournal Pro is a comprehensive trading journal application built for managing and analyzing stock trades. The application provides traders with tools to track their trades, monitor watchlists, analyze performance metrics, and maintain a portfolio overview. It features a modern dark-themed interface with real-time data capabilities and comprehensive trade management functionality.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client-side is built using React with TypeScript, utilizing a modern component-based architecture. The application uses Vite as the build tool and development server, providing fast hot module replacement and optimized production builds. React Router (wouter) handles client-side navigation between different pages including Dashboard, Trades, Analytics, Watchlist, and Portfolio.

The UI is constructed using shadcn/ui components built on top of Radix UI primitives, providing accessible and customizable components. Tailwind CSS handles styling with a custom dark theme configuration. The application uses TanStack Query (React Query) for server state management, data fetching, and caching, which provides optimistic updates and background synchronization.

### Backend Architecture
The server is built with Express.js and TypeScript, following a RESTful API design pattern. The application uses a layered architecture with route handlers, storage abstraction, and middleware for logging and error handling. The server implements CRUD operations for trades and watchlist management, along with analytics endpoints for performance calculations.

The storage layer uses an abstraction pattern with an interface (IStorage) that can be implemented by different storage backends. Currently, it includes an in-memory storage implementation for development, but the architecture supports easy migration to database storage solutions.

### Data Layer and Schema Management
The application uses Drizzle ORM for database schema definition and type-safe database operations. The schema is shared between client and server through a shared module, ensuring type consistency across the full stack. Database schemas are defined for trades and watchlist symbols with proper relationships and constraints.

Zod is used for runtime validation and schema generation, providing type-safe form handling and API request/response validation. The schema definitions include validation rules for trade data, ensuring data integrity throughout the application.

### State Management and Data Flow
Client-side state management is handled through TanStack Query for server state and React's built-in state management for local UI state. The application follows a unidirectional data flow pattern where user actions trigger API calls, which update the server state and automatically refresh the client-side cache.

Forms are managed using React Hook Form with Zod validation, providing a robust form handling solution with proper error management and user feedback.

### Component Architecture
The application follows a modular component structure with reusable UI components, page-specific components, and business logic components. Components are organized into logical directories including layout components, trading-specific components, and shared UI components.

The layout uses a responsive sidebar navigation pattern that adapts to mobile devices with an overlay drawer approach. The main content area uses a card-based layout for displaying different sections of information.

## External Dependencies

### UI and Styling
- **Radix UI**: Provides accessible, unstyled UI primitives for building the component library
- **Tailwind CSS**: Utility-first CSS framework for styling with custom dark theme configuration
- **shadcn/ui**: Pre-built component library built on Radix UI with consistent design patterns
- **Lucide React**: Icon library providing consistent iconography throughout the application

### Data Management
- **Drizzle ORM**: Type-safe ORM for PostgreSQL database operations and schema management
- **Neon Database**: Serverless PostgreSQL database for cloud-based data storage
- **TanStack Query**: Powerful data synchronization library for React applications
- **Zod**: TypeScript-first schema validation library for runtime type checking

### Development and Build Tools
- **Vite**: Fast build tool and development server with hot module replacement
- **TypeScript**: Static type checking for both client and server code
- **ESBuild**: Fast JavaScript bundler for production builds
- **React Hook Form**: Performant forms library with minimal re-renders

### Backend Infrastructure
- **Express.js**: Web application framework for Node.js providing RESTful API capabilities
- **tsx**: TypeScript execution environment for running server code in development

The application is designed to be deployed on Replit with environment-based configuration for database connections and API integrations. The architecture supports easy scaling and deployment to production environments with minimal configuration changes.