# TRIVENTA - Phase 1 MVP

A startup platform built with React and Firebase featuring a complete identity system.

## 🚀 Features Implemented

### 🔐 Authentication System
- **Email + Password Signup**: User registration with validation
- **Login**: Secure authentication with Firebase
- **Logout**: Clean session management
- **Protected Routes**: Authentication guards for sensitive pages

### 👥 Role Selection System
- **Mandatory Role Selection**: After signup, users must select a role
- **Three Roles Available**:
  - 👩‍💻 **Founder** (Purple badge) - Build startups
  - 💰 **Investor** (Green badge) - Fund startups  
  - 👥 **User** (Blue badge) - Explore & give feedback
- **Role Storage**: User roles saved in Firestore database

### 👤 Profile System
- **Profile Display**: Shows user information with role badge
- **Dynamic Role Badges**: Color-coded badges for each role type
- **Profile Images**: Auto-generated avatars based on email
- **Activity Section**: Ready for future feature expansion

### 🎨 Premium UI/UX
- **Modern Design**: Clean, professional interface with gradients
- **Responsive Layout**: Mobile-friendly design
- **Smooth Interactions**: Hover effects and transitions
- **Bottom Navigation**: App-style navigation bar
- **Premium Styling**: Professional color scheme and typography

## 📁 Project Structure

```
src/
├── components/
│   └── RoleBadge.jsx          # Reusable role badge component
├── contexts/
│   └── AuthContext.jsx        # Authentication context
├── pages/
│   ├── Login.jsx              # Login page
│   ├── Signup.jsx             # Registration page
│   ├── RoleSelect.jsx         # Role selection page
│   ├── Home.jsx               # Main dashboard
│   └── Profile.jsx            # User profile page
├── firebase.js                # Firebase configuration
└── App.jsx                    # Main app with routing
```

## 🗄️ Database Structure (Firestore)

### Users Collection
```javascript
{
  id: "user_uid",           // Auto-generated
  name: "username",         // Extracted from email
  email: "user@example.com",
  role: "founder|investor|user",
  bio: "",                  // Empty by default
  profileImage: "url",      // Auto-generated avatar
  createdAt: timestamp      // Registration timestamp
}
```

## 🎯 User Flow

1. **Landing** → Login or Signup
2. **Signup** → Email/password registration
3. **Role Selection** → Choose role (Founder/Investor/User)
4. **Home Dashboard** → Main platform interface
5. **Profile** → View personal information with role badge

## 🛠️ Tech Stack

- **Frontend**: React 19 with functional components and hooks
- **Backend**: Firebase (Authentication + Firestore)
- **Routing**: React Router DOM
- **Styling**: Inline styles with modern CSS properties
- **Build Tool**: Vite

## 🚀 Getting Started

1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Start Development Server**:
   ```bash
   npm run dev
   ```

3. **Open Browser**: Navigate to `http://localhost:5173`

## 🔧 Firebase Configuration

Firebase is already configured with:
- Authentication (Email/Password)
- Firestore Database
- Web app configuration

## 🎨 Role Badge System

The `RoleBadge` component is a critical reusable component that:
- **Displays role** with appropriate colors
- **Sizing Options**: Small, Medium (default), Large
- **Color Coding**:
  - Founder: Purple (#8B5CF6)
  - Investor: Green (#10B981)
  - User: Blue (#3B82F6)
- **Usage**: Can be used throughout the app for consistent role display

## 📱 Mobile Responsiveness

- **Responsive Design**: All pages adapt to mobile screens
- **Touch-Friendly**: Appropriate touch targets for mobile
- **Bottom Navigation**: Mobile-style navigation bar

## 🔒 Security Features

- **Protected Routes**: Authentication guards on sensitive pages
- **Role Validation**: Users must complete role selection
- **Firebase Security**: Built-in Firebase authentication security
- **Input Validation**: Client-side validation on forms

## 🚧 Next Steps (Phase 2)

The foundation is ready for:
- Post creation system
- User interactions
- Advanced profile features
- Real-time updates
- File uploads
- Advanced search

## 🎯 Key Achievements

✅ **Complete Authentication Flow**: Signup → Login → Logout  
✅ **Role-Based System**: Mandatory role selection with badges  
✅ **Database Integration**: Firestore with proper data structure  
✅ **Premium UI**: Modern, clean, professional design  
✅ **Mobile Responsive**: Works on all device sizes  
✅ **Reusable Components**: RoleBadge component for consistency  
✅ **Protected Routes**: Proper authentication guards  

---

**TRIVENTA Phase 1 MVP** - Ready for user testing and Phase 2 development! 🚀
