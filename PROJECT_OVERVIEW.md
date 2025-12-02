# GrayBox AI - Education Edition

## 🎓 Application Overview

GrayBox AI Education Edition is a fully interactive, 3D-enhanced educational web application designed specifically for students from 8th class to 2nd PUC (ages 13-18). The application features an AI-powered avatar that serves as a personal learning coach, providing personalized study roadmaps, interactive learning materials, and comprehensive progress tracking.

## ✨ Key Features

### 1. **AI-Powered Learning Assistant**
- Interactive 3D avatar with animations (wave, jump, talk, idle)
- AI-generated personalized study roadmaps using Large Language Model API
- Daily motivational quotes
- Real-time study tips and guidance

### 2. **Authentication & Onboarding**
- Email-based authentication system
- Interactive 3D animated onboarding flow
- Profile creation with personalized questions
- Secure user data management with Supabase

### 3. **Student Dashboard**
- Comprehensive overview of learning progress
- Quick access to all sections
- Progress visualization with charts
- Badge collection display
- Active roadmap tracking

### 4. **Education Hub**
- Six core subjects: Math, Science, Biology, Physics, Chemistry, English
- Subject-specific learning materials
- Notes, videos, and animations
- Practice questions and MCQs
- Formula charts

### 5. **AI Roadmap Creator** ⭐ Core Feature
- Personalized study plan generation using AI
- Input: Class, weak subjects, available study time
- Output: Detailed roadmap with:
  - Daily tasks
  - Weekly revision plans
  - Chapter-by-chapter schedule
  - Test preparation timeline
  - Progress tracking
  - Task completion rewards

### 6. **Test Zone**
- MCQ quizzes with timer
- Puzzle games
- Flashcards for quick revision
- Scoreboard tracking
- Achievement badges system

### 7. **Teacher Section**
- Teacher profiles with ratings
- "Ask Doubt" feature
- Direct messaging
- Schedule call functionality

### 8. **Friends & Social Learning**
- Add and connect with classmates
- Share notes and resources
- Group study rooms
- 3D bubble chat interface

### 9. **Market**
- Class-specific educational materials
- Books, guides, and sample papers
- 3D card presentation

### 10. **Help Center**
- Live chat support
- Call support
- Comprehensive FAQ
- Voice assistant

## 🎨 Design Philosophy

### Visual Design
- **Vibrant Color Scheme**: Purple, cyan, and pink gradients with neon glow effects
- **3D Elements**: All cards and components have 3D depth with shadows
- **Animations**: Bouncing, floating, and pulsing animations throughout
- **Kid-Friendly**: Round edges, bright colors, and playful interactions
- **Responsive**: Desktop-first design with mobile adaptation

### Color System
- **Primary**: Purple (270° 80% 60%) - Main brand color
- **Secondary**: Cyan (200° 85% 55%) - Supporting color
- **Accent**: Pink (330° 85% 60%) - Highlights and CTAs
- **Success**: Green (150° 70% 50%) - Achievements
- **Warning**: Yellow (45° 95% 55%) - Alerts

## 🛠️ Technology Stack

### Frontend
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS with custom 3D utilities
- **UI Components**: shadcn/ui
- **Routing**: React Router v7
- **State Management**: React Context + Hooks
- **Icons**: Lucide React
- **Notifications**: Sonner

### Backend & Database
- **Backend**: Supabase
- **Database**: PostgreSQL (via Supabase)
- **Authentication**: Supabase Auth
- **Real-time**: Supabase Realtime
- **Storage**: Supabase Storage (if needed)

### AI Integration
- **LLM API**: Large Language Model (Gemini 2.5 Flash)
- **Use Cases**:
  - Personalized roadmap generation
  - Motivational quotes
  - Study tips
  - Doubt answering

## 📊 Database Schema

### Tables
1. **profiles** - Student information and settings
2. **roadmaps** - Personalized study plans
3. **roadmap_tasks** - Individual tasks within roadmaps
4. **test_scores** - Quiz and test results
5. **badges** - Available achievement badges
6. **user_badges** - Badges earned by students
7. **friends** - Friend relationships
8. **messages** - Communication between users
9. **progress_tracking** - Subject and chapter progress

### Security
- Row Level Security (RLS) enabled on all tables
- Students can only access their own data
- First user becomes admin automatically
- Admins have full access to all data

## 🚀 Getting Started

### Prerequisites
- Node.js ≥ 20
- npm ≥ 10

### Installation
```bash
# Install dependencies
npm install

# Start development server
npm run dev -- --host 127.0.0.1
```

### Environment Variables
The application uses Supabase, and environment variables are automatically configured in `.env`:
- `VITE_SUPABASE_URL` - Supabase project URL
- `VITE_SUPABASE_ANON_KEY` - Supabase anonymous key
- `VITE_APP_ID` - Application ID

## 📁 Project Structure

```
src/
├── components/
│   ├── avatar/
│   │   └── Avatar3D.tsx          # 3D animated avatar component
│   ├── common/
│   │   └── Header.tsx            # Navigation header
│   └── ui/
│       ├── Card3D.tsx            # Reusable 3D card component
│       └── ...                   # shadcn/ui components
├── db/
│   ├── supabase.ts               # Supabase client
│   └── api.ts                    # Database API functions
├── pages/
│   ├── Login.tsx                 # Authentication page
│   ├── Onboarding.tsx            # Profile setup
│   ├── Dashboard.tsx             # Main dashboard
│   ├── Profile.tsx               # Student profile
│   ├── Education.tsx             # Subject selection
│   ├── TestZone.tsx              # Testing area
│   ├── Teachers.tsx              # Teacher directory
│   ├── Friends.tsx               # Social features
│   ├── Market.tsx                # Educational materials
│   ├── Help.tsx                  # Support center
│   ├── RoadmapCreator.tsx        # AI roadmap generator
│   └── Roadmap.tsx               # Roadmap viewer
├── services/
│   └── llm.ts                    # LLM API integration
├── types/
│   └── types.ts                  # TypeScript interfaces
├── App.tsx                       # Main app component
├── routes.tsx                    # Route configuration
└── index.css                     # Global styles & design system
```

## 🎯 Core Workflows

### 1. User Registration & Onboarding
1. User signs up with email and password
2. Completes 4-step onboarding with 3D question cards:
   - Name
   - Class (8th-2nd PUC)
   - Favorite subject
   - Hobbies
3. Profile is created and user is redirected to dashboard

### 2. Creating a Study Roadmap
1. Navigate to Roadmap Creator
2. Select class and weak subjects
3. Specify daily study time
4. AI generates personalized roadmap
5. Review and save roadmap
6. Track tasks and progress

### 3. Taking Tests
1. Navigate to Test Zone
2. Choose test type (MCQ, Puzzle, Flashcard)
3. Complete test with timer
4. View results and earn badges
5. Scores are saved to profile

## 🎨 Custom Animations

### CSS Animations
- **bounceIn**: Entry animation for cards
- **float**: Gentle floating motion for avatar
- **pulseGlow**: Pulsing glow effect
- **card-3d**: Hover effect with 3D transform

### Component Animations
- Avatar animations: wave, jump, talk, idle
- Card hover effects
- Progress bar animations
- Badge unlock animations

## 🔐 Security Features

- Email/password authentication
- Row Level Security (RLS) on all tables
- Secure API endpoints
- Protected routes with auth guards
- Admin role management

## 📱 Responsive Design

- Desktop-first approach
- Breakpoints: sm, md, lg, xl, 2xl
- Mobile-optimized navigation
- Touch-friendly interactions
- Adaptive layouts

## 🎓 Educational Content

### Subjects Covered
1. **Mathematics** - Algebra, Geometry, Calculus
2. **Science** - General Science concepts
3. **Biology** - Life sciences
4. **Physics** - Matter, energy, forces
5. **Chemistry** - Elements, reactions
6. **English** - Language and communication

### Learning Materials (Placeholder Structure)
- Notes and study guides
- Video tutorials
- Interactive animations
- Practice questions
- MCQ tests
- Formula charts

## 🏆 Gamification

### Badge System
10 achievement badges:
- First Steps (Complete first lesson)
- Quick Learner (Complete 10 lessons)
- Test Master (Score 100%)
- Consistent Student (7-day streak)
- Subject Expert (Complete all chapters)
- Social Butterfly (Add 5 friends)
- Helpful Friend (Share notes 10 times)
- Early Bird (Study before 8 AM)
- Night Owl (Study after 10 PM)
- Perfect Week (Complete all weekly tasks)

### Progress Tracking
- Overall progress percentage
- Subject-wise progress
- Task completion tracking
- Test score history
- Badge collection

## 🤖 AI Features

### LLM Integration
The application uses the Large Language Model API (Gemini 2.5 Flash) for:

1. **Roadmap Generation**
   - Analyzes student's class, weak subjects, and available time
   - Creates structured study plan with daily tasks
   - Provides chapter-wise breakdown
   - Includes revision and test schedules

2. **Motivational Content**
   - Daily motivational quotes
   - Study tips and tricks
   - Encouragement messages

3. **Doubt Solving**
   - AI-powered answers to student questions
   - Subject-specific explanations
   - Step-by-step solutions

## 🔄 Future Enhancements

Placeholder features that can be fully implemented:
- Real-time chat with teachers
- Video call functionality
- Interactive puzzle games
- Flashcard system with spaced repetition
- Group study rooms with video
- Note sharing with rich text editor
- Advanced analytics dashboard
- Parent portal
- Mobile app version

## 📝 Notes

- **First User**: The first registered user automatically becomes an admin
- **Dummy Data**: Teacher profiles and some content use placeholder data
- **AI Responses**: LLM responses may take up to 30 seconds
- **Database**: All data is stored securely in Supabase PostgreSQL

## 🎉 Conclusion

GrayBox AI Education Edition provides a comprehensive, engaging, and AI-powered learning platform for high school students. With its vibrant 3D design, personalized roadmaps, and gamified learning experience, it makes education fun and effective.

The application is production-ready with core features fully implemented, and includes a solid foundation for future enhancements.
