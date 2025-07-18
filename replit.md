# Yugmi Sense - Construction Inspection Mobile App

## Overview

Yugmi Sense is a mobile-first Progressive Web Application (PWA) designed for construction site inspection and monitoring. The application enables users to capture photos and videos, leverage AI-powered analysis to detect structural issues and safety concerns, and generate comprehensive inspection reports. Built with a modern full-stack architecture, it provides real-time insights for construction professionals.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query (React Query) for server state and caching
- **UI Framework**: Radix UI components with Tailwind CSS styling
- **Design System**: shadcn/ui component library with custom theming
- **Build Tool**: Vite for fast development and optimized builds
- **Mobile-First**: Responsive design optimized for mobile devices with PWA capabilities

### Backend Architecture
- **Runtime**: Node.js with Express.js server
- **Language**: TypeScript with ES modules
- **API Design**: RESTful API with structured error handling
- **File Handling**: Multer for media upload processing with size limits (50MB)
- **Development**: Hot module replacement with Vite middleware integration

### Data Storage Solutions
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon serverless PostgreSQL
- **Schema Management**: Drizzle Kit for migrations and schema management
- **Connection**: Connection pooling with @neondatabase/serverless
- **File Storage**: Local filesystem storage for uploaded media files

### AI Integration
- **AI Provider**: Google Gemini 2.5 Pro API
- **Capabilities**: 
  - Image analysis for construction inspection
  - Video analysis for dynamic assessments
  - Issue detection with severity classification
  - Structural element identification
  - Safety hazard recognition

## Key Components

### Media Management System
- **Upload Processing**: Multi-format support (JPEG, PNG, GIF, MP4, MOV, AVI)
- **Metadata Capture**: GPS coordinates, location names, timestamps
- **Storage**: Organized file system with unique identifiers
- **Validation**: File type and size restrictions for security

### Camera Integration
- **Live Camera**: Real-time video preview with device camera access
- **Capture Modes**: Photo and video recording capabilities
- **Camera Controls**: Front/back camera switching, flash toggle
- **Geolocation**: Automatic location tagging for captured media

### AI Analysis Engine
- **Image Processing**: Detailed structural analysis including:
  - Foundation, walls, beams, and support structures
  - Electrical components and wiring
  - Plumbing systems and fixtures
  - Building materials assessment
  - Crack and damage detection
- **Issue Classification**: Severity levels (low, medium, high, critical)
- **Confidence Scoring**: AI confidence metrics for analysis reliability

### Report Generation
- **Customizable Reports**: Configurable inclusion of images, issues, and location data
- **Date Range Filtering**: Time-based report generation
- **Export Capabilities**: Structured report output with media attachments
- **Status Tracking**: Draft, in-progress, and completed report states

### Mobile Navigation
- **Bottom Navigation**: Primary navigation for dashboard, camera, gallery, and reports
- **Responsive Design**: Optimized for mobile viewport with touch-friendly interactions
- **Progressive Enhancement**: Works across various device capabilities

## Data Flow

1. **Media Capture**: Users capture photos/videos through the camera interface
2. **Upload Processing**: Files are validated, stored, and metadata extracted
3. **AI Analysis**: Media is automatically sent to Gemini API for analysis
4. **Data Storage**: Results are stored in PostgreSQL with relationships maintained
5. **Visualization**: Processed data is displayed in gallery and dashboard views
6. **Report Generation**: Users can compile data into structured reports

## External Dependencies

### Core Infrastructure
- **Database**: Neon PostgreSQL for serverless database hosting
- **AI Service**: Google Gemini API for image and video analysis
- **Geocoding**: OpenStreetMap Nominatim for address resolution

### Development Tools
- **Replit Integration**: Cartographer plugin for development environment
- **Error Handling**: Runtime error overlay for development debugging
- **Type Safety**: Comprehensive TypeScript coverage across client and server

### Security Considerations
- **File Validation**: Strict MIME type and extension checking
- **Size Limits**: 50MB upload limit to prevent abuse
- **Input Sanitization**: Validated data schemas using Zod
- **Environment Variables**: Secure configuration management

## Deployment Strategy

### Development Environment
- **Hot Reload**: Vite development server with Express middleware
- **Database Migrations**: Drizzle Kit for schema management
- **Environment Setup**: Automated Replit integration with banner support

### Production Build
- **Client Build**: Vite production build with optimized assets
- **Server Build**: ESBuild compilation for Node.js deployment
- **Static Assets**: Separate client and server build outputs
- **Process Management**: Single process serving both API and static files

### Configuration Management
- **Environment Variables**: Database URL, Gemini API key configuration
- **Build Scripts**: Automated development, build, and deployment workflows
- **Type Checking**: Pre-deployment TypeScript validation

The architecture prioritizes mobile performance, offline capability potential, and seamless integration between AI analysis and user workflows, making it suitable for field-based construction inspection scenarios.