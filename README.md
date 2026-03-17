# FindItBack.ac.in
## MIT & MEC Campus Lost & Found Platform
### Built by a student, for students 💛

---

## 📁 Project Structure

```
FindItBack/
├── index.html              ← LOGIN PAGE (open this first!)
├── css/
│   └── style.css           ← All styles
├── js/
│   ├── firebase-config.js  ← ⚠️ PUT YOUR FIREBASE CONFIG HERE
│   ├── app.js              ← Shared utilities (session, toast, nav)
│   ├── auth.js             ← Login & Register logic
│   ├── lost.js             ← Submit Lost Item + auto-match
│   ├── found.js            ← Submit Found Item + auto-match
│   └── dashboard.js        ← Admin dashboard + verify + contacts
└── pages/
    ├── home.html           ← Main page after login
    ├── lost.html           ← Report Lost Item form
    ├── found.html          ← Report Found Item form
    └── dashboard.html      ← Admin Dashboard
```

---

## 🚀 How to Run in VS Code

### Step 1 — Open in VS Code
1. Open VS Code
2. File → Open Folder → Select the `FindItBack` folder

### Step 2 — Install Live Server (one time only)
1. Click Extensions icon in VS Code (or press Ctrl+Shift+X)
2. Search for "Live Server" by Ritwick Dey
3. Click Install

### Step 3 — Run the website
1. Right-click on `index.html`
2. Click "Open with Live Server"
3. Browser opens at `http://127.0.0.1:5500`

---

## 🔥 Firebase Setup (to store real data)

### Step 1 — Create Firebase Project
1. Go to https://firebase.google.com
2. Click "Add project" → Name it `FindItBack` → Create project

### Step 2 — Enable Firestore Database
1. In Firebase console, click "Firestore Database"
2. Click "Create database"
3. Select "Start in test mode" (allows read/write for 30 days)
4. Click "Enable"

### Step 3 — Get your config
1. Click ⚙️ gear icon → "Project settings"
2. Scroll to "Your apps" section
3. Click the `</>` Web icon
4. Register app name as "FindItBack"
5. Copy the `firebaseConfig` object

### Step 4 — Paste config into the project
1. Open `js/firebase-config.js` in VS Code
2. Replace these values with your real ones:
   ```js
   apiKey:            "YOUR_API_KEY",        ← replace
   authDomain:        "YOUR_PROJECT_ID.firebaseapp.com", ← replace
   projectId:         "YOUR_PROJECT_ID",     ← replace
   storageBucket:     "YOUR_PROJECT_ID.appspot.com",     ← replace
   messagingSenderId: "YOUR_SENDER_ID",      ← replace
   appId:             "YOUR_APP_ID"          ← replace
   ```

### Step 5 — Test it!
1. Open the website
2. Register a new account
3. Submit a Lost Item report
4. Submit a Found Item report with same category
5. Go to Dashboard → You'll see both reports and a "Potential Match" badge!

---

## 🔐 How Login Works

- **Register**: Creates account saved in browser's localStorage
- **Login**: Requires Name + Campus (MIT/MEC) + Email + Password
- **Demo Login**: Click "Demo Login" to try without registering
- **Session**: Stays logged in until you click Logout

---

## ⚡ How Auto-Matching Works

When a report is submitted, the system:
1. Queries all unmatched reports from the **same campus**
2. Scores each against the new report:
   - Same category = **+40 points**
   - Matching words in item name = **+20 points each**
   - Matching words in description = **+5 points each**
3. If best score ≥ 40 → marks both as **"Potential Match"**
4. Admin then verifies ownership via Q&A
5. After confirmation → contacts are shared → item returned!

---

## 📤 How to Share With Friends

### Option 1 — Netlify (Easiest, free, 2 minutes)
1. Go to https://netlify.com → Sign up free
2. Drag the entire `FindItBack` folder onto the Netlify dashboard
3. Get a live URL like `finditback.netlify.app`
4. Share the link!

### Option 2 — GitHub Pages (free)
1. Create account at github.com
2. Create new repository called `finditback`
3. Upload all files
4. Settings → Pages → Enable → Live at `yourusername.github.io/finditback`

---

## 🎓 About FindItBack

Built by a student of Mahendra Institute of Technology (MIT) who found a silver bracelet on campus one day and had no way to return it. That one moment became this platform.

**The mission**: Everyone has the power to build something useful for the people around them.

---

*FindItBack.ac.in — MIT & MEC Campus · Built by a student, for students 💛*
