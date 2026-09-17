# 🗓️ Sync-Up - Availability Calendar

A fast, beautiful, and real-time collaborative calendar web application designed to eliminate group-chat scheduling friction. Create an event calendar, share the link with friends, and instantly find the best days everyone is free.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/Vanilla_CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase_Realtime_DB-FFCA28?style=flat&logo=firebase&logoColor=black)
![PWA](https://img.shields.io/badge/PWA-Ready-success?style=flat&logo=pwa)

---

## ✨ Features

- **⚡ Real-Time Group Synchronization**: Powered by Firebase Realtime Database. As soon as a friend marks their availability, your screen updates instantly without refreshing.
- **📲 Installable Progressive Web App (PWA)**: Installable on iOS and Android home screens with offline caching, native Web Share API, and haptic feedback.
- **🌓 Dark Mode & Auto-Stretching Layout**: Integrated theme toggle with instant anti-FOUC bootstrap, fluid screen height fitting with zero scrolling, and bottom-pinned share action.
- **🔥 Best Days Consensus Ranking**: Automatically analyzes group availability and highlights the top dates with highest consensus and a star badge.
- **🎨 Rich Modern Aesthetics**: Clean glassmorphism cards, Google Fonts (`Plus Jakarta Sans`), tailored color palette, and dynamic avatar color hashing per participant name.
- **🔍 Day Detail & Inspection Modal**: Tap any day to inspect the full list of friends available on that date and easily toggle your own attendance.
- **🔗 1-Click Deep Linking**: Directly invite friends via `?room=CalendarName`. If they're a new visitor, they simply enter their name and land straight into the shared calendar.
- **🕒 Jump to Today & Recent History**: Quick navigation back to today's date, and a recent room list stored in `localStorage` for switching between hangouts with one click.
- **📱 Mobile Optimized**: Responsive grid layout that handles touch devices and high-density screens smoothly.

---

## 🚀 Getting Started

### 1. Running Locally
Because Sync-Up is built as a zero-dependency static web application, you can run it directly:
- Simply double-click `index.html` or open it in any web browser.
- Or use any local server:
  ```bash
  # Using Python
  python -m http.server 8080

  # Or using Node / npx
  npx serve .
  ```

### 2. Firebase Configuration
The application is pre-configured to connect to Firebase Realtime Database. If you wish to use your own Firebase project:
1. Go to the [Firebase Console](https://console.firebase.google.com/).
2. Create a project and set up a **Realtime Database**.
3. In `index.html`, replace `firebaseConfig` with your credentials:
   ```javascript
   const firebaseConfig = {
       apiKey: "YOUR_API_KEY",
       authDomain: "YOUR_PROJECT.firebaseapp.com",
       databaseURL: "https://YOUR_PROJECT-default-rtdb.firebaseio.com/",
       projectId: "YOUR_PROJECT",
       storageBucket: "YOUR_PROJECT.firebasestorage.app",
       messagingSenderId: "...",
       appId: "..."
   };
   ```
4. Set database security rules to allow read/write for your room paths:
   ```json
   {
     "rules": {
       "calendars": {
         ".read": true,
         ".write": true
       }
     }
   }
   ```

---

## 📋 How It Works

1. **Enter Your Name**: Introduce yourself with your display name.
2. **Open or Create a Calendar**: Type a room name (e.g., `HawaiiTrip`, `DNDCampaign`) or pick from your recent calendars.
3. **Mark Availability**: Click any date to view details and mark yourself available.
4. **Share**: Click **Copy Calendar Share Link** and send it into your group chat.
