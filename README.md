# BillBuddy 5 — Full + Gmail Detected (Expo Router, SDK 51)

Light-blue theme • Offline storage • Tabs for Calendar / Tracker / Missed / Comments / Detected • Add/Edit bills • Notifications ready • Gmail proposals (backend-ready).

## Install & Run
```bash
npm install
npx expo start
```

## Build APK (EAS)
```bash
eas build -p android --profile production
```

## Backend endpoints (expected)
- `GET /api/proposals` → `{ proposals: [{ id, merchant, amount, preview, repeat, dueDate, endDate, messageId }] }`
- `POST /api/proposals/:id/accept`
- `POST /api/proposals/:id/reject`
- `GET /auth/google` (optional) — launches OAuth to connect Gmail

If no backend is available, the Detected screen will show "No backend detected (offline fallback)".

## Files
- `app/(tabs)/detected.js` — Gmail proposals (Accept/Reject/Refresh/Connect Gmail)
- `lib/storage.js` — `API_BASE` = `http://localhost:8080` (change anytime)
