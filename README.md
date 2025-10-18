# 📱 BillBuddy 5 — Smart Bill & Payment Manager

**BillBuddy 5** helps you stay on top of your bills, loans, and subscriptions.  
Track upcoming payments, view monthly totals, get reminders, and even detect bills automatically from Gmail or digital contracts.

---

## 🌟 Features

| Category | What it does |
|-----------|---------------|
| 🗓 **Calendar View** | See all your bills by due date with monthly totals (Due / Paid). |
| 💸 **Add & Edit Bills** | Add one-time or repeating payments (weekly, bi-weekly, every 30 days, monthly, yearly). |
| 📊 **Tracker** | Track ongoing loans and installments — shows how much is left to pay. |
| ❗ **Missed Payments** | Lists overdue bills and lets you mark them as paid. |
| 💬 **Comments** | Add personal notes or reminders to each bill and search through them. |
| 🕵️ **Detected Contracts** | Automatically detects new bills from Gmail or uploaded contract text (when backend is connected). |
| 🔔 **Reminders & Notifications** | Local notifications for upcoming and missed bills (requires permission). |
| 🔒 **Offline Support** | Works completely offline — data saved securely on your device. |
| ☁️ **Optional Backend Sync** | Ready to connect to a backend for Gmail integration and cloud storage. |

---

## 🧭 Getting Started

### 1. Install dependencies
```bash
npm install
```

### 2. Run in development mode
```bash
npx expo start
```
Then open the QR code in **Expo Go** on your Android or iOS device.

### 3. Build for Android
```bash
eas build -p android --profile production
```

You’ll get an APK or AAB ready to install on your phone.

---

## ⚙️ App Structure (Expo Router)

```
app/
 ├─ (tabs)/                 → Main tabs
 │   ├─ index.js            → Calendar
 │   ├─ tracker.js          → Loan Tracker
 │   ├─ missed.js           → Missed Payments
 │   ├─ comments.js         → Notes / Comments
 │   └─ detected.js         → Gmail & Contracts (backend-ready)
 │
 ├─ addbill.js              → Add / Edit Bill screen
 └─ notifications.js        → Handles notification permissions

lib/
 └─ storage.js              → Local data storage & helper functions
assets/
 ├─ icon.png (1024×1024)
 └─ splash.png (1280×720)
```

---

## 🔌 Backend Integration (Advanced)

If you connect your own API server (Node, Flask, etc.), BillBuddy will automatically show detected bills from Gmail or uploaded documents.

| Endpoint | Method | Description |
|-----------|--------|-------------|
| `/api/proposals` | GET | Returns list of detected bills |
| `/api/proposals/:id/accept` | POST | Accepts and saves a detected bill |
| `/api/proposals/:id/reject` | POST | Rejects a proposal |
| `/auth/google` | GET | Launches Gmail OAuth (optional) |

Edit `API_BASE` in `lib/storage.js` to point to your backend URL.

---

## 🔔 Notifications

- You’ll be asked for permission the first time the app runs.  
- If enabled, notifications will remind you about upcoming or missed bills.  
- On Android, BillBuddy 5 uses a default notification channel.

---

## 🧱 Data & Storage

- Data is saved locally using **AsyncStorage** (secure local database).  
- Bills, comments, and settings persist between sessions.  
- You can clear local data anytime by uninstalling the app.

---

## 🎨 Design

- **Theme:** Light-blue / white (modern Google-style aesthetic)  
- **Icons:** Clean minimalist style for each tab  
- **Fonts:** Default system font for maximum compatibility  

---

## 🧑‍💻 Developer Notes

- Built with **Expo SDK 51**  
- Routing via **Expo Router v3**  
- Notifications via **expo-notifications**  
- Offline persistence via **@react-native-async-storage/async-storage**

---

## ❤️ Tips

- Always keep your Expo CLI and EAS CLI updated.  
- If the app doesn’t open, ensure you’re using the same SDK version listed in `package.json`.  
- You can safely replace `API_BASE` with your live backend later.

---

## 📄 License

BillBuddy 5 is provided for personal and educational use.  
Commercial redistribution requires permission from the developer.
