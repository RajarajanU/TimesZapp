# TimesZapp - Minutz AI

An AI-powered social media aggregator with a personal AI assistant. Unify all your social networks into one intelligent dashboard with real-time voice chat, trend detection, and smart notifications.

![TimesZapp](client/public/favicon.png)

## Features

### Minutz AI Assistant
- ChatGPT-like conversational AI powered by OpenAI
- Voice chat with natural-sounding responses via ElevenLabs
- Voice cloning — create a personal AI voice from your own recordings
- Multi-turn conversations with context preservation
- Smart intent detection for automatic tool invocation

### Unified Social Dashboard
- Connect Gmail, Facebook, Instagram, LinkedIn, WhatsApp, and Twitter/X
- Unified feed from all connected networks
- AI-analyzed trends with sentiment analysis
- Daily digest generation across all platforms

### Mr Techie — Autonomous Tech News Agent
- Fetches top 10 technology news insights every hour
- Covers AI & Machine Learning, Cybersecurity, Web Development, Cloud Computing, Startups, and more
- Browser push notifications for hourly tech updates

### Document Generation
- Create resumes, cover letters, and professional documents
- Export in multiple formats: Word (.docx), PDF, Excel (.xlsx), PowerPoint (.pptx), Plain Text

### Smart Camera & Vision
- Built-in camera with AI-powered image analysis
- Auto-scanning mode for real-time visual understanding

### Customization
- Theme switching (Light / Dark / System)
- Voice style and gender selection
- Compact mode
- Push notification controls

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, TypeScript, Vite, Tailwind CSS v4 |
| UI Components | shadcn/ui (Radix UI), Framer Motion |
| Routing | Wouter |
| State Management | TanStack Query (React Query) |
| Backend | Express.js, TypeScript, Node.js |
| Database | PostgreSQL with Drizzle ORM |
| AI | OpenAI API (GPT-4o) |
| Voice | ElevenLabs TTS, Web Speech API |
| Auth | Custom token-based authentication with bcrypt |

## Prerequisites

- Node.js 18+
- PostgreSQL database
- OpenAI API key
- ElevenLabs API key (for voice features)
- Google OAuth credentials (for Gmail integration)

## Environment Variables

Create a `.env` file in the root directory:

```env
DATABASE_URL=postgresql://user:password@host:port/database
OPENAI_API_KEY=your_openai_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
PGHOST=your_db_host
PGPORT=5432
PGUSER=your_db_user
PGPASSWORD=your_db_password
PGDATABASE=your_db_name
```

## Installation

```bash
# Clone the repository
git clone https://github.com/your-username/timeszapp.git
cd timeszapp

# Install dependencies
npm install

# Push database schema
npm run db:push

# Start development server
npm run dev
```

The app will be available at `http://localhost:5000`.

## Project Structure

```
timeszapp/
├── client/                  # Frontend React application
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   ├── hooks/           # Custom React hooks
│   │   │   ├── use-audio-capture.ts    # Voice recording & speech recognition
│   │   │   ├── use-speech-synthesis.ts # Text-to-speech & voice settings
│   │   │   └── use-push-notifications.ts
│   │   ├── lib/             # Utilities and API client
│   │   └── pages/           # Page components
│   │       └── dashboard.tsx # Main application dashboard
│   └── index.html
├── server/                  # Backend Express application
│   ├── ai.ts               # OpenAI integration & system prompt
│   ├── ai-tools.ts         # AI function calling tools
│   ├── documents.ts        # Document generation (Word, PDF, Excel, PPT)
│   ├── elevenlabs.ts       # ElevenLabs voice API integration
│   ├── mr-techie.ts        # Autonomous tech news agent
│   ├── routes.ts           # API route definitions
│   ├── storage.ts          # Database operations (Drizzle ORM)
│   └── index.ts            # Server entry point
├── shared/
│   └── schema.ts           # Database schema (shared between client & server)
├── package.json
├── vite.config.ts
├── drizzle.config.ts
└── tsconfig.json
```

## API Endpoints

### Authentication
- `POST /api/auth/register` — Create a new account
- `POST /api/auth/login` — Sign in
- `POST /api/auth/forgot-password` — Request password reset

### Conversations & Messages
- `GET /api/conversations` — List conversations
- `POST /api/conversations` — Create conversation
- `GET /api/conversations/:id/messages` — Get messages
- `POST /api/conversations/:id/messages` — Send message & get AI response

### Connected Services
- `GET /api/services` — List connected services
- `POST /api/services/connect` — Connect a service
- `DELETE /api/services/:id` — Disconnect a service

### Voice
- `POST /api/voice/tts` — Text-to-speech via ElevenLabs
- `GET /api/voice/voices` — List available voices
- `POST /api/voice/clone` — Clone a voice from audio samples

### Tech News
- `GET /api/tech-news` — Get tech news articles
- `GET /api/tech-news/current` — Get current hour's news

### Vision
- `POST /api/vision/analyze` — Analyze an image with AI

## Scripts

```bash
npm run dev        # Start development server with hot reload
npm run build      # Build for production
npm run db:push    # Push database schema changes
```

## License

MIT

---

Built with Minutz AI

