# ZenMind Financial Assistant

A comprehensive WhatsApp-based financial assistant platform that helps users manage their finances through conversational AI.

## Project Overview

ZenMind Financial Assistant is a monorepo containing multiple integrated components that work together to provide a seamless financial management experience via WhatsApp.

### Components

- **`zenmind-website/`** - Next.js marketing website and landing page
- **`whatsapp-integration/`** - WhatsApp Business API webhook service for message handling

## Architecture

```
┌─────────────────┐     ┌─────────────────┐
│                 │     │                 │
│  ZenMind Website│     │  WhatsApp Users │
│   (Next.js)     │     │                 │
│                 │     │                 │
└────────┬────────┘     └────────┬────────┘
         │                       │
         │                       │ Messages
         │                       │
         │              ┌────────▼────────┐
         │              │                 │
         └──────────────┤ WhatsApp        │
                        │ Integration     │
                        │ Service         │
                        │                 │
                        └─────────────────┘
```

## Quick Start

### Prerequisites

- Node.js 18+ and npm
- WhatsApp Business Account
- Meta Developer Account
- Vercel account (for website deployment)
- Railway account (for webhook service deployment)

### Local Development

1. Clone the repository:
```bash
git clone https://github.com/yourusername/zenmind-financial-assistant.git
cd zenmind-financial-assistant
```

2. Install dependencies for all components:
```bash
# Install website dependencies
cd zenmind-website
npm install

# Install WhatsApp integration dependencies
cd ../whatsapp-integration
npm install
```

3. Set up environment variables:

For `zenmind-website/`:
- No environment variables needed for basic setup

For `whatsapp-integration/`:
Create a `.env` file with:
```env
WHATSAPP_BUSINESS_ACCOUNT_ID=your_business_account_id
META_APP_SECRET=your_app_secret
TEST_PHONE_NUMBER_ID=your_phone_number_id
TEST_ACCESS_TOKEN=your_access_token
WEBHOOK_VERIFY_TOKEN=your_verify_token
PORT=3000
```

4. Run the services:

```bash
# Terminal 1 - Website
cd zenmind-website
npm run dev

# Terminal 2 - WhatsApp Integration
cd whatsapp-integration
npm start
```

## Deployment

### Website Deployment (Vercel)

1. Install Vercel CLI: `npm i -g vercel`
2. From `zenmind-website/` directory: `vercel`
3. Follow the prompts to deploy
4. Configure custom domain in Vercel dashboard

### WhatsApp Integration Deployment (Railway)

1. Connect your GitHub repository to Railway
2. Configure environment variables in Railway dashboard
3. Deploy from main branch

## Features

### Current Features
- Professional landing page with service information
- WhatsApp webhook integration
- Message receipt and storage
- Conversation window tracking (24-hour rule)
- Webhook signature verification

### Planned Features
- AI-powered financial advice
- Expense tracking and categorization
- Budget management
- Financial goal setting
- Investment recommendations
- Bill reminders
- Financial reports and insights

## Development Workflow

1. Create feature branches from `main`
2. Make changes in the appropriate component directory
3. Test locally before committing
4. Create pull requests for review
5. Merge to `main` after approval

## Project Structure

```
zenmind-financial-assistant/
├── README.md                    # This file
├── .gitignore                   # Root gitignore
├── zenmind-website/             # Marketing website
│   ├── app/                     # Next.js app directory
│   ├── public/                  # Static assets
│   ├── package.json             # Website dependencies
│   └── README.md                # Website-specific docs
├── whatsapp-integration/        # WhatsApp webhook service
│   ├── index.js                 # Main server file
│   ├── webhookHandler.js        # Webhook logic
│   ├── messageStore.js          # Message storage
│   ├── package.json             # Service dependencies
│   └── README.md                # Service-specific docs
└── docs/                        # Additional documentation
    ├── customer-strategy.md     # Customer acquisition strategy
    └── whatsapp-financial-assistant-mvp-plan.md
```

## Testing

### Website Testing
```bash
cd zenmind-website
npm run build  # Build check
npm run lint   # Linting
```

### WhatsApp Integration Testing
```bash
cd whatsapp-integration
npm run test-send  # Send test message
npm run test-info  # Get phone info
```

## Security Considerations

- All WhatsApp webhooks are verified using Meta's signature verification
- Environment variables are used for sensitive data
- HTTPS is required for production deployments
- Follow Meta's WhatsApp Business API security best practices

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is proprietary and confidential. All rights reserved.

## Support

For questions or support, please contact the development team.

## Links

- [Website](https://www.zenmind.com.br)
- [WhatsApp Business API Documentation](https://developers.facebook.com/docs/whatsapp/business-api)
- [Next.js Documentation](https://nextjs.org/docs)

---

Built with ❤️ by the ZenMind team