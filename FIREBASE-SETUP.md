# 🔥 Firebase Authentication Setup Guide

## ⚠️ IMPORTANT - AUTHENTICATION NOT ENABLED

The login/signup is not working because **Firebase Authentication is not enabled** in your Firebase console.

## 🚀 QUICK FIX (5 minutes)

### 1. Go to Firebase Console
- Visit: https://console.firebase.google.com/
- Select your project: `triventa-e114a`

### 2. Enable Authentication
- Go to **Authentication** → **Sign-in method**
- Click **Email/Password**
- Enable **Email/Password** provider
- Save

### 3. Configure Firestore Rules
- Go to **Firestore Database** → **Rules**
- Replace with:
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
    match /posts/{postId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null && request.auth.uid == resource.data.userId;
    }
    match /comments/{commentId} {
      allow read: if request.auth != null;
      allow write: if request.auth != null;
    }
  }
}
```
- Publish

### 4. Configure Storage Rules
- Go to **Storage** → **Rules**
- Replace with:
```javascript
rules_version = '2';
service firebase.storage {
  match /b/{bucket}/o {
    match /posts/{userId}/{allPaths=**} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
```
- Publish

## 🔍 Test After Setup

Once enabled, you can test:
1. **Signup**: Create new account
2. **Login**: Use created credentials
3. **Role Selection**: Choose your role
4. **Home Feed**: Access main platform

## 🛠️ Debug Features Added

Enhanced error messages now show:
- ✅ Specific Firebase error codes
- ✅ Network issues
- ✅ Account status problems
- ✅ Configuration issues

## 📱 Current Status

- ✅ Firebase Config: Connected
- ✅ Components: Built
- ✅ UI: Complete
- ❌ Authentication: NOT ENABLED (needs setup)

**Complete the Firebase setup above and authentication will work!**
