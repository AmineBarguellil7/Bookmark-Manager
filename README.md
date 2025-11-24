# Bookmark Manager

A modern web application for organizing and managing your personal bookmarks with authentication and a clean, responsive interface.

## What It Does

Bookmark Manager is a secure, user-authenticated bookmarking application that allows you to save, organize, and manage your favorite web links. Each user has their own private collection of bookmarks with titles, URLs, and optional notes.

## Tech Stack

- **Next.js 16** (App Router) - React framework with server-side rendering
- **Clerk** - Authentication and user management
- **Prisma** - Database ORM with SQLite
- **TypeScript** - Type-safe development
- **React 19** - UI library

## Key Features

- 🔐 **User Authentication** - Secure sign-in/sign-up with Clerk
- ➕ **Add Bookmarks** - Save bookmarks with URL, title, and optional notes
- 📋 **View Bookmarks** - Browse your bookmarks in a responsive card grid
- 🗑️ **Delete Bookmarks** - Remove bookmarks with confirmation
- 🔒 **User Isolation** - Each user only sees and manages their own bookmarks
- ⚡ **Real-time Updates** - Optimistic UI updates for instant feedback

## How It Works

The application follows a client-server architecture:

1. **Client Side**: React components use a custom `useBookmarks` hook to manage state and interact with the API
2. **API Routes**: Next.js API routes handle GET, POST, and DELETE requests with Clerk authentication
3. **Database Layer**: Prisma utilities query SQLite database, ensuring users can only access their own bookmarks
4. **Authentication**: Clerk middleware protects routes and provides user context throughout the application

## Getting Started

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Set up environment variables:**
   Create a `.env.local` file with your Clerk keys and database URL:
   ```
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_key
   CLERK_SECRET_KEY=your_secret
   DATABASE_URL="file:./dev.db"
   ```

3. **Set up the database:**
   ```bash
   npx prisma generate
   npx prisma db push
   ```

4. **Run the development server:**
   ```bash
   npm run dev
   ```

5. **Open your browser:**
   Navigate to [http://localhost:3000](http://localhost:3000)

## Future Enhancements

- Tagging and categorization system
- Search and filter functionality
- Edit existing bookmarks
- Bookmark folders/collections
- Import/export bookmarks
- Sharing bookmarks with other users
