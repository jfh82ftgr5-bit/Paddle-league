Paddle League — Push Notifications V2 (OneSignal setup)

ONESIGNAL APP ID:
1418ad78-7e8d-4833-ba12-2579bea70e29

THIS UPDATE INSTALLS:
- OneSignal Web SDK v16
- Combined OneSignal + Paddle League service worker in sw.js
- Required PWA manifest fields and app icons for iPhone Home Screen installation
- "Enable Phone Notifications" button in Account > Settings
- iPhone Add-to-Home-Screen instructions when needed
- OneSignal External ID linked to the signed-in Paddle League user
- Existing Notifications V1 in-app bell and settings remain

IMPORTANT IPHONE STEPS AFTER DEPLOY:
1. Open https://paddle-league2.vercel.app in Safari/Chrome/Edge.
2. Use Share > Add to Home Screen.
3. Open Paddle League FROM THE HOME SCREEN ICON.
4. Sign in.
5. Account > Settings > Enable Phone Notifications.
6. Tap Allow on the iPhone notification permission prompt.

ONESIGNAL DASHBOARD:
After these files are live, return to OneSignal and tap "I've installed the SDK".
The SDK/subscription side will then be ready for a test push.

AUTOMATIC SERVER PUSH:
This package connects devices to OneSignal. Automatic lock-screen delivery for every Supabase notification still needs the OneSignal App API Key stored securely on the server. Do NOT put that private key in index.html or GitHub.
We will do that server-only step after OneSignal confirms the SDK installation.

UPLOAD:
This update contains 7 files instead of 5 because iPhone web push requires installed-app icons:
- index.html
- manifest.webmanifest
- sw.js
- vercel.json
- README.txt
- icon-192.png
- icon-512.png

Upload/replace all 7 files in the GitHub Paddle-league repository root and commit to main.
