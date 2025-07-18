# Yugmi Sense - Construction Inspection Mobile App

A mobile-first Progressive Web Application (PWA) designed for construction site inspection and monitoring with AI-powered analysis capabilities.

## 🏗️ Overview

Yugmi Sense enables construction professionals to capture photos and videos, leverage AI-powered analysis to detect structural issues and safety concerns, and generate comprehensive inspection reports. The application provides real-time insights for construction site monitoring and quality assurance.

## ✨ Features

### 📱 Mobile-First Design
- Progressive Web App (PWA) capabilities
- Responsive design optimized for mobile devices
- Touch-friendly interface with intuitive navigation
- Offline capability potential

### 📸 Media Capture & Management
- Real-time camera integration with live preview
- Photo and video recording capabilities
- Front/back camera switching with flash controls
- Automatic GPS location tagging
- Multi-format support (JPEG, PNG, GIF, MP4, MOV, AVI)
- File size validation (50MB limit)

### 🤖 AI-Powered Analysis
- **Google Gemini 2.5 Pro Integration** for intelligent analysis
- **Structural Assessment**: Foundation, walls, beams, support structures
- **Systems Analysis**: Electrical components, plumbing fixtures
- **Material Evaluation**: Building materials assessment
- **Damage Detection**: Crack identification and severity analysis
- **Safety Monitoring**: Hazard recognition and classification
- **Confidence Scoring**: AI reliability metrics

### 📊 Inspection Reports
- Customizable report generation
- Date range filtering capabilities
- Export functionality with media attachments
- Status tracking (draft, in-progress, completed)
- Structured output with detailed analysis

### 🗺️ Location Services
- Automatic geolocation capture
- Address resolution via OpenStreetMap Nominatim
- Location-based organization of inspections

## 🛠️ Technology Stack

### Frontend
- **React 18** with TypeScript
- **Wouter** for lightweight client-side routing
- **TanStack Query** for server state management and caching
- **Radix UI** components with Tailwind CSS styling
- **shadcn/ui** component library
- **Vite** for fast development and optimized builds
- **Framer Motion** for smooth animations

### Backend
- **Node.js** with Express.js server
- **TypeScript** with ES modules
- **Multer** for file upload processing
- **RESTful API** design with structured error handling

### Database & Storage
- **PostgreSQL** with Drizzle ORM
- **Neon** serverless PostgreSQL hosting
- **Drizzle Kit** for migrations and schema management
- Local filesystem storage for media files

### AI & External Services
- **Google Gemini 2.5 Pro API** for image and video analysis
- **OpenStreetMap Nominatim** for geocoding services

## 🚀 Getting Started

### Prerequisites
- Node.js 20 or higher
- PostgreSQL database (or Neon account)
- Google Gemini API key

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd yugmi-sense
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   Create a `.env` file in the root directory:
   ```env
   DATABASE_URL=your_postgresql_connection_string
   GEMINI_API_KEY=your_google_gemini_api_key
   NODE_ENV=development
   PORT=5000
   ```

4. **Database Setup**
   ```bash
   npm run db:push
   ```

5. **Start Development Server**
   ```bash
   npm run dev
   ```

The application will be available at `http://localhost:5000`

### Build for Production

```bash
npm run build
npm start
```

## 📁 Project Structure

```
yugmi-sense/
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/         # Application pages/routes
│   │   ├── hooks/         # Custom React hooks
│   │   ├── lib/           # Utility functions
│   │   └── index.css      # Global styles
│   └── index.html         # HTML entry point
├── server/                # Backend Express server
│   └── index.ts          # Server entry point
├── shared/               # Shared types and schemas
│   └── schema.ts         # Database schema definitions
├── migrations/           # Database migration files
├── components.json       # shadcn/ui configuration
├── drizzle.config.ts    # Database configuration
├── tailwind.config.ts   # Tailwind CSS configuration
├── vite.config.ts       # Vite build configuration
└── package.json         # Project dependencies
```

## 🔧 Available Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run check` - Run TypeScript type checking
- `npm run db:push` - Push database schema changes

## 🏗️ Architecture

### Data Flow
1. **Media Capture**: Users capture photos/videos through camera interface
2. **Upload Processing**: Files are validated, stored, and metadata extracted
3. **AI Analysis**: Media is sent to Gemini API for intelligent analysis
4. **Data Storage**: Results stored in PostgreSQL with maintained relationships
5. **Visualization**: Processed data displayed in gallery and dashboard
6. **Report Generation**: Users compile data into structured reports

### Security Features
- File validation with strict MIME type checking
- Upload size limits (50MB) to prevent abuse
- Input sanitization using Zod schemas
- Secure environment variable management

### Mobile Optimization
- Touch-friendly interface design
- Optimized for various screen sizes
- Progressive enhancement approach
- Efficient media handling for mobile networks

## 🔌 API Endpoints

### Health Check
- `GET /api/health` - Server health status

### Media Management
- `POST /api/media/upload` - Upload photos/videos
- `GET /api/media` - Retrieve media files
- `GET /api/media/:id` - Get specific media file

### AI Analysis
- `POST /api/analysis` - Trigger AI analysis
- `GET /api/analysis/:id` - Get analysis results

### Reports
- `POST /api/reports` - Generate inspection report
- `GET /api/reports` - List all reports
- `GET /api/reports/:id` - Get specific report

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 Development Guidelines

### Code Style
- Use TypeScript for type safety
- Follow React best practices
- Implement responsive design patterns
- Write meaningful commit messages

### Testing
- Test on multiple mobile devices
- Verify camera functionality across browsers
- Validate AI analysis accuracy
- Test offline capabilities

## 🐛 Troubleshooting

### Common Issues

**Camera not working**
- Ensure HTTPS connection (required for camera access)
- Check browser permissions for camera access
- Verify device camera availability

**Upload failures**
- Check file size (must be under 50MB)
- Verify supported file formats
- Ensure stable internet connection

**AI analysis errors**
- Verify Gemini API key configuration
- Check API rate limits
- Ensure image quality is sufficient

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Google Gemini AI for intelligent analysis capabilities
- Radix UI for accessible component primitives
- Tailwind CSS for utility-first styling
- Neon for serverless PostgreSQL hosting
- OpenStreetMap for geocoding services

## 📞 Support

For support and questions, please open an issue in the GitHub repository or contact the development team.

---

Built with ❤️ for construction professionals worldwide.