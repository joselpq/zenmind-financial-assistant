# ZenMind Financial Assistant

AI-powered financial advisor accessible via WhatsApp, designed to help Brazilians manage their finances and build better money habits.

## 🎯 Mission

Democratize financial education and planning for lower-income Brazilians by providing personalized financial advice through WhatsApp - the platform they already use daily.

## 🏗️ Architecture

```
┌─────────────────┐         ┌──────────────────┐         ┌─────────────────┐
│                 │         │                  │         │                 │
│  Landing Page   │────────▶│  WhatsApp API    │────────▶│   PostgreSQL    │
│   (Next.js)     │         │   Integration    │         │    Database     │
│                 │         │   (Express.js)   │         │                 │
└─────────────────┘         └──────────────────┘         └─────────────────┘
     Vercel                      Railway                      Railway
       │                           │
       │                           │
       ▼                           ▼
┌─────────────────┐         ┌──────────────────┐
│                 │         │                  │
│     Users       │         │  WhatsApp Users  │
│   (Website)     │         │   (+55 11...)    │
│                 │         │                  │
└─────────────────┘         └──────────────────┘
```

## 📁 Project Structure

```
Financial Assistant/
├── zenmind-website/        # Landing page (Next.js)
│   ├── app/               # App router pages
│   ├── public/            # Static assets
│   └── package.json       # Dependencies
│
├── whatsapp-integration/   # WhatsApp API service
│   ├── src/               # Source code
│   ├── database/          # SQL schemas
│   ├── scripts/           # Setup utilities
│   └── server.js          # Main server
│
└── README.md              # This file
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Git
- Railway account (for deployment)
- Vercel account (for website)
- WhatsApp Business account

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/joselpq/Financial-Assistant.git
   cd Financial-Assistant
   ```

2. **Website setup:**
   ```bash
   cd zenmind-website
   npm install
   npm run dev
   # Opens at http://localhost:3000
   ```

3. **WhatsApp service setup:**
   ```bash
   cd ../whatsapp-integration
   npm install
   cp .env.example .env  # Configure your credentials
   npm run dev
   # Runs at http://localhost:3000
   ```

## 💬 WhatsApp Integration

### Current Features
- ✅ Webhook integration with Meta/WhatsApp
- ✅ Message persistence in PostgreSQL
- ✅ 24-hour conversation window tracking
- ✅ Automatic template/free message routing
- ✅ Basic auto-responses from Arnaldo

### Test the Integration
1. Send a WhatsApp message to **+55 11 93904-1011**
2. Receive an auto-response from Arnaldo
3. Check health status at: https://whatsapp-integration-production-06bb.up.railway.app/health

## 🌐 Website

Live at: https://zenmind.com.br

### Features
- WhatsApp-first CTAs
- Trust elements and testimonials
- Mobile-optimized design
- Direct WhatsApp integration

## 🛠️ Technology Stack

- **Frontend:** Next.js 14, React, Tailwind CSS
- **Backend:** Express.js, Node.js
- **Database:** PostgreSQL
- **Deployment:** Vercel (website), Railway (API)
- **APIs:** WhatsApp Business API, Meta Graph API

## 📊 Current Status

### ✅ Completed
- Landing page with WhatsApp CTAs
- WhatsApp webhook integration
- Database setup and message persistence
- Basic conversation flow
- Production deployment

### 🚧 In Progress
- AI financial assistant (Arnaldo)
- Advanced conversation flows
- Financial planning features

### 📋 Planned
- Expense tracking via WhatsApp
- Savings goals and reminders
- Financial education content
- Integration with Brazilian payment systems

## 🔐 Security & Privacy

- All messages encrypted in transit
- PostgreSQL database with secure access
- No financial data stored without consent
- LGPD compliant practices

## 👥 Team

- **Product:** Define requirements and user experience
- **Engineering:** Build and maintain the platform
- **Arnaldo:** Your AI financial assistant

## 🤝 Contributing

This is a private repository. Team members should:
1. Create feature branches from `main`
2. Make pull requests for review
3. Deploy after approval

## 📞 Support

- **Technical issues:** Check Railway/Vercel logs
- **Product questions:** Contact product team
- **User support:** Via WhatsApp

---

**Remember our mission:** Make financial planning accessible to every Brazilian, one WhatsApp message at a time. 🇧🇷 💚