# ConstructPro - Construction Management System

## Overview

ConstructPro is a comprehensive construction management system built with modern web technologies. It provides a complete solution for managing construction projects, budgets, contracts, cash flow, and clients. The application features a React frontend with a Node.js/Express backend, using PostgreSQL for data persistence and Drizzle ORM for database operations.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Components**: Radix UI primitives with shadcn/ui components
- **Styling**: Tailwind CSS with CSS variables for theming
- **State Management**: TanStack Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Replit Auth (OpenID Connect)
- **Session Management**: Express sessions with PostgreSQL storage
- **File Generation**: PDFKit for PDF generation, Nodemailer for emails

### Key Components

1. **Authentication System**
   - Replit Auth integration with OpenID Connect
   - Session-based authentication with PostgreSQL storage
   - Role-based access control (admin/user)

2. **Database Layer**
   - Drizzle ORM for type-safe database operations
   - PostgreSQL with Neon database provider
   - Schema-driven development with migrations

3. **API Layer**
   - RESTful API endpoints for all business operations
   - Express middleware for authentication and logging
   - Structured error handling and validation

4. **UI Components**
   - Modular component architecture
   - Consistent design system with shadcn/ui
   - Form components with validation
   - Data tables with CRUD operations

## Data Flow

1. **Client Request**: User interacts with React components
2. **API Call**: TanStack Query handles HTTP requests to Express API
3. **Authentication**: Middleware verifies user session
4. **Database Operation**: Drizzle ORM executes database queries
5. **Response**: Data flows back through the same path
6. **UI Update**: React components re-render with new data

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL database connection
- **@radix-ui/react-***: UI primitive components
- **@tanstack/react-query**: Server state management
- **drizzle-orm**: Database ORM
- **nodemailer**: Email sending service
- **pdfkit**: PDF document generation
- **passport**: Authentication middleware

### Development Dependencies
- **vite**: Build tool and dev server
- **typescript**: Type checking
- **tailwindcss**: CSS framework
- **@types/***: Type definitions

## Deployment Strategy

### Build Process
1. **Frontend Build**: Vite builds React app to `dist/public`
2. **Backend Build**: esbuild bundles server code to `dist/index.js`
3. **Database**: Drizzle migrations ensure schema is up-to-date

### Environment Variables
- `DATABASE_URL`: PostgreSQL connection string
- `SESSION_SECRET`: Session encryption key
- `SMTP_HOST`, `SMTP_USER`, `SMTP_PASS`: Email configuration
- `REPLIT_DOMAINS`: Allowed domains for auth
- `ISSUER_URL`: OpenID Connect issuer URL

### Production Considerations
- Session storage in PostgreSQL for scalability
- Static file serving for production builds
- Environment-specific configurations
- Database migrations for schema updates

## Business Logic

### Core Modules
1. **Clients**: Customer management with contact information
2. **Templates**: Reusable budget templates for different service types
3. **Budgets**: Project cost estimates with itemized breakdowns
4. **Contracts**: Service agreements linked to approved budgets
5. **Cash Flow**: Financial transaction tracking and reporting

### Key Features
- PDF generation for budgets and contracts
- Email notifications for client communications
- Role-based permissions for different user types
- Responsive design for mobile and desktop use
- Real-time data synchronization across components

### Data Relationships
- Clients can have multiple budgets and contracts
- Budgets can be converted to contracts
- Templates provide base structure for budgets
- Transactions can be linked to contracts for tracking
- All entities maintain audit trails with timestamps