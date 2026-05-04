# TRIVENTA Deployment Guide

## Phase 9 - Scalability & Security

### Prerequisites
- Node.js 18+
- Firebase CLI
- Git

---

## Environment Setup

### 1. Development
```bash
# Copy environment template
cp .env.example .env.development

# Fill in your Firebase dev project credentials
# Edit .env.development with your values

# Install dependencies
npm install

# Start dev server
npm run dev
```

### 2. Production
```bash
# Copy production environment
cp .env.example .env.production

# Fill in production Firebase credentials
# Edit .env.production with production values
```

---

## Firebase Setup

### 1. Create Firebase Project
```bash
firebase login
firebase init
```

### 2. Deploy Firestore Rules
```bash
firebase deploy --only firestore:rules
```

### 3. Deploy Firestore Indexes
```bash
firebase deploy --only firestore:indexes
```

---

## Build & Deploy

### Build for Production
```bash
npm run build
```

### Deploy to Firebase Hosting
```bash
firebase deploy --only hosting
```

### Deploy Everything
```bash
firebase deploy
```

---

## Data Backup Strategy

### Automated Backup (Recommended)
Set up Firebase's automated backup:

1. Go to Firebase Console > Firestore Database
2. Click "Export/Import"
3. Set up scheduled exports to Cloud Storage

### Manual Backup
```bash
# Export Firestore data
firebase firestore:export ./backups/$(date +%Y%m%d)
```

### Restore from Backup
```bash
# Import Firestore data
firebase firestore:import ./backups/YYYYMMDD
```

---

## Security Checklist

- [ ] Firestore rules deployed
- [ ] Firestore indexes deployed
- [ ] Environment variables set
- [ ] Debug logs disabled in production
- [ ] Rate limiting enabled
- [ ] Admin users configured
- [ ] Backup schedule configured

---

## Monitoring

### System Health
Check system health:
```javascript
// In browser console
await monitoringService.healthCheck()
```

### View Logs
Access system logs in Firebase Console:
1. Firestore Database
2. `systemLogs` collection

---

## Scaling Considerations

### Database
- Pagination enabled (20 items/page)
- Indexed queries for performance
- Denormalized data for reads

### Security
- Rate limiting (client-side)
- Firestore rules enforced
- Role-based access control

### Performance
- Lazy loading images
- Optimized queries with limits
- Real-time listeners cleaned up

---

## Support

For issues, check:
1. Firebase Console logs
2. Browser console errors
3. systemLogs collection
