# Harry Potter House Quiz [https://harry-potter-house-quiz.org]

A magical Harry Potter-themed quiz application built with Next.js 15, featuring interactive quizzes for sorting hat, patronus discovery, and character identification. Discover your Hogwarts house, find your Patronus, and see which character you're most like!

![preview](preview.png)

## ✨ Features

### 🎩 Interactive Quizzes
- **Sorting Hat Quiz**: Discover your Hogwarts house through Quick Sort or Chat Mode with AI-powered analysis
- **Patronus Quiz**: Find your magical guardian spirit with 20 unique Patronus forms
- **Character Quiz**: Discover which Harry Potter character matches your personality

### 🌍 Multi-language Support
- **Languages**: English, Chinese (中文), German (Deutsch), Spanish (Español), Arabic (العربية)
- **SEO Optimized**: Metadata and content optimized for each language with user-friendly search terms
- **Localized Content**: All quizzes, descriptions, and UI elements fully translated

### 🤖 AI-Powered Features
- **AI Chat**: Real-time conversations with the Sorting Hat and Harry Potter characters
- **Multiple AI Providers**: Support for OpenAI, DeepSeek, Replicate, and OpenRouter
- **Smart Analysis**: Advanced personality assessment algorithms

### 👤 User Features
- **Authentication**: Google OAuth via NextAuth.js
- **Save Results**: Store quiz results in your profile
- **Test History**: View all your quiz results over time
- **Social Sharing**: Share your results with friends

### 🎨 Modern UI/UX
- **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- **Magical Animations**: Framer Motion animations for an immersive experience
- **Dark Mode**: Theme switching support
- **Accessibility**: Built with Radix UI primitives

### 📊 Admin Dashboard
- **Content Management**: Manage quizzes, categories, and blog posts
- **User Management**: View and manage user accounts
- **Analytics**: Track quiz completions and user engagement

## 🚀 Tech Stack

- **Framework**: Next.js 15.2.8 with App Router
- **Runtime**: React 19
- **Language**: TypeScript (strict mode)
- **Styling**: Tailwind CSS 4.1.4
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: NextAuth.js 5.0.0-beta.25
- **Internationalization**: next-intl
- **UI Components**: Radix UI primitives
- **Animations**: Framer Motion
- **Payment**: Stripe
- **Email**: Resend
- **Deployment**: Vercel (primary), Cloudflare Workers

## 📦 Quick Start

### Prerequisites

- Node.js 18+ 
- pnpm (recommended) or npm
- PostgreSQL database
- Environment variables (see `.env.example`)

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/your-username/harry-potter-house-quiz-org.git
cd harry-potter-house-quiz-org
```

2. **Install dependencies**

```bash
pnpm install
```

3. **Set up environment variables**

```bash
cp .env.example .env.development
```

Edit `.env.development` with your configuration:
- Database connection string
- NextAuth secrets and OAuth credentials
- AI provider API keys
- Stripe keys (if using payments)
- Resend API key (for emails)

4. **Set up the database**

```bash
# Generate migrations
pnpm db:generate

# Run migrations
pnpm db:migrate

# Or push schema directly (development)
pnpm db:push
```

5. **Run the development server**

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📁 Project Structure

```
src/
├── app/[locale]/           # Next.js App Router with i18n
│   ├── (admin)/           # Admin dashboard routes
│   ├── (default)/         # Public-facing pages
│   │   ├── sorting-hat-quiz/
│   │   ├── patronus-quiz/
│   │   ├── character-quiz/
│   │   ├── harry-potter-memes/
│   │   └── posts/         # Blog posts
│   └── auth/              # Authentication pages
├── components/            # Reusable React components
│   ├── blocks/           # Layout blocks
│   ├── ui/               # UI primitives (Shadcn)
│   ├── sorting-hat-quiz/
│   ├── patronus-quiz/
│   └── character-quiz/
├── db/                    # Database schema and configuration
│   ├── schema.ts         # Drizzle schema definitions
│   └── migrations/       # Database migrations
├── i18n/                  # Internationalization
│   ├── messages/         # Global translations
│   └── pages/            # Page-specific translations
├── lib/                   # Utility functions
├── services/              # Business logic services
├── types/                 # TypeScript type definitions
├── hooks/                 # Custom React hooks
├── models/                # Data models
└── auth/                  # NextAuth configuration
```

## 🛠️ Development

### Available Scripts

```bash
# Development
pnpm dev              # Start dev server with Turbopack
pnpm build            # Build for production
pnpm start            # Start production server
pnpm lint             # Run ESLint

# Database
pnpm db:generate      # Generate Drizzle migrations
pnpm db:migrate       # Run database migrations
pnpm db:push          # Push schema changes (dev)
pnpm db:studio        # Open Drizzle Studio

# SEO Verification
pnpm seo:verify-all   # Verify all SEO configurations

# Bundle Analysis
ANALYZE=true pnpm build  # Analyze bundle size
```

### Customization

#### Theme
Edit `src/app/theme.css` to customize colors and styling.

#### Landing Page
Update content in `src/i18n/pages/landing/` for each language.

#### Translations
- Global messages: `src/i18n/messages/`
- Page-specific: `src/i18n/pages/`

## 🌐 SEO Optimization

This project includes comprehensive SEO optimizations:

- **Metadata**: Optimized titles and descriptions for each language
- **Hreflang Tags**: Proper language and region targeting
- **Canonical URLs**: Prevent duplicate content issues
- **Structured Data**: Rich snippets for better search visibility
- **Sitemap**: Auto-generated sitemap for all pages
- **User-Friendly Keywords**: Content optimized with common search terms

### SEO Verification Scripts

```bash
pnpm seo:verify-hreflang-comprehensive  # Verify hreflang tags
pnpm seo:verify-reciprocal              # Check reciprocal hreflang
pnpm seo:verify-duplicates              # Find duplicate hreflang
pnpm seo:verify-canonical               # Verify canonical URLs
pnpm seo:verify-all                    # Run all checks
```

## 🚢 Deployment

### Deploy to Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fyour-username%2Fharry-potter-house-quiz-org)

1. Push your code to GitHub
2. Import project in Vercel
3. Configure environment variables
4. Deploy!

### Deploy to Cloudflare Workers

For Cloudflare deployment, use the `cloudflare` branch:

```bash
git clone -b cloudflare https://github.com/your-username/harry-potter-house-quiz-org.git
# or for existing project
git checkout cloudflare
```

1. Configure environment variables:
```bash
cp .env.example .env.production
cp wrangler.toml.example wrangler.toml
```

2. Edit `.env.production` and add variables to `wrangler.toml` under `[vars]`

3. Deploy:
```bash
npm run cf:deploy
```

### Docker Deployment

```bash
# Build image
pnpm docker:build

# Run container
docker run -p 3000:3000 harry-potter-house-quiz-org:latest
```

## 📚 Documentation

Detailed documentation is available in the `docs/` directory:

- [Sorting Hat Quiz](docs/SORTING_HAT_QUIZ_PAGE.md)
- [Character Chat Setup](docs/CHARACTER_CHAT_SETUP.md)
- [SEO Implementation](docs/SEO_IMPLEMENTATION_REVIEW.md)
- [Hreflang Guide](docs/HREFLANG_COMPLETE_GUIDE.md)
- [Performance Optimization](docs/PERFORMANCE_OPTIMIZATION_SUMMARY.md)
- [Database Troubleshooting](docs/DATABASE_CONNECTION_TROUBLESHOOTING.md)

## 🎯 Key Features Details

### Sorting Hat Quiz
- **Quick Sort**: Write freely about yourself, AI analyzes and determines your house
- **Chat Mode**: Real-time conversation with the Sorting Hat
- **Detailed Analysis**: Get 3-5 reasons for your house assignment

### Patronus Quiz
- **20 Unique Forms**: From stag to phoenix, discover your guardian spirit
- **Personality-Based**: Advanced algorithm matches your traits
- **Detailed Profiles**: Learn about your Patronus's meaning and symbolism

### Character Quiz
- **9 Iconic Characters**: Match with Harry, Hermione, Ron, Dumbledore, and more
- **Comprehensive Analysis**: Multi-dimensional personality assessment
- **Character Profiles**: Detailed information about each character

## 🔐 Security

- Environment variables never exposed to client
- CSRF protection via NextAuth.js
- Content Security Policy configured
- Secure authentication flow
- SQL injection prevention via Drizzle ORM
- Input validation with Zod schemas

## 📝 License

See [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📧 Support

For issues and questions, please open an issue on GitHub.

## 🙏 Acknowledgments

- Built with [Next.js](https://nextjs.org/)
- UI components from [Radix UI](https://www.radix-ui.com/)
- Styling with [Tailwind CSS](https://tailwindcss.com/)
- Icons from [React Icons](https://react-icons.github.io/react-icons/)

---

Made with ✨ magic and ❤️ for Harry Potter fans worldwide!
