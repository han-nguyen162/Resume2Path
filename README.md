Resume2Path

Resume2Path is an end-to-end AI-powered web application that helps users analyze resumes, extract key skills, identify gaps, and generate actionable career recommendations. Built with Next.js, TypeScript, Tailwind CSS, and powered by OpenAI GPT-4-mini, this project showcases a full-stack implementation with a focus on scalability and user experience.

<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/3bbb6cda-f8e5-4627-b7f1-eb8f86953218" />

## 🚀 Quick Start

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Set up environment variables**
   ```bash
   cp env.example .env.local
   # Edit .env.local with your actual values
   ```

3. **Set up database**
   ```bash
   npm run db:generate
   npm run db:push
   ```

4. **Run development server**
   ```bash
   npm run dev
   ```

5. **Open [http://localhost:3000](http://localhost:3000)**

## 🔧 Environment Variables

Create a `.env.local` file with:

```env
# OpenAI API Key for GPT-4o-mini
OPENAI_API_KEY=your_openai_api_key_here

# Gemini API Key
GEMINI_API_KEY=your_google_gemini_key_here

# Vercel Postgres Database URL
POSTGRES_URL=your_vercel_postgres_url_here

# Vercel Blob Storage Token
BLOB_READ_WRITE_TOKEN=your_vercel_blob_token_here

# Your app URL (for production)
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Optional: Resend API Key for email functionality
# RESEND_API_KEY=your_resend_api_key_here

# Firebase config
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key_here
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_auth_domain_here
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id_here
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_storage_bucket_here
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id_here
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id_here

# MongoDB Connection String
MONGODB_URI=mongodb://localhost:27017/resume2review
```

## 🏗️ Architecture

### Stack
- **Frontend**: Next.js 14 (App Router, TypeScript)
- **Styling**: Tailwind CSS + shadcn/ui
- **Database**: Vercel Postgres + Drizzle ORM
- **Storage**: Vercel Blob
- **AI**: OpenAI GPT-4o-mini
- **Deployment**: Vercel

### Database Schema
- `mentees`: User information (email, name, target role)
- `resumes`: Resume files and parsed content
- `analyses`: AI analysis results (skills, gaps, suggestions)

### Flow
1. User uploads CV on `/upload`
2. File processed via `/api/upload`
3. AI extracts skills and identifies gaps
4. Results displayed on `/analysis/[id]`
5. CTA to book 1-on-1 session

## 📁 Project Structure

```
src/
├── app/
│   ├── api/upload/route.ts    # File upload & AI processing
│   ├── analysis/[id]/page.tsx # Analysis results
│   ├── globals.css            # Global styles
│   ├── layout.tsx             # Root layout
│   └── page.tsx               # Upload form
├── components/ui/             # shadcn/ui components
├── db/                        # Database schema & connection
└── lib/                       # Utility functions
```

## 🚀 Deployment

1. **Push to GitHub**
2. **Connect to Vercel**
3. **Set environment variables in Vercel dashboard**
4. **Deploy!**

## 🔮 Future Enhancements

- Email notifications (Resend)
- Stripe checkout integration
- Mentor dashboard
- Advanced PDF annotation
- Queue system for heavy processing

## 📝 License

MIT

