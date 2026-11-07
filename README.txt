PADDLE LEAGUE — LOCK SCREEN NOTIFICATION URL FIX V2
November 7, 2026

ROOT CAUSE FOUND:
The live Supabase send-push Edge Function already includes a URL such as:
https://paddle-league2.vercel.app/?notification=<notification UUID>
Previous code listened for the OneSignal JavaScript click event, but the
installed iPhone PWA can launch through the URL without firing that event.
The app did not read the notification query parameter, so only the app opened.

FIX:
- Read the notification ID from the push launch URL on startup, page show,
  history navigation, and focus.
- After account loading, look up that ID in this account's notifications,
  then use Paddle League's existing notification routing to open the profile.
- Remove the one-time URL parameter to avoid stale repeated navigation.
- Preserve existing OneSignal configuration, permissions and service worker.
- No Supabase Edge Function changes or database migrations required.

INSTALL:
Replace the same 5 files in your GitHub repository's root (main branch):
index.html, manifest.webmanifest, sw.js, vercel.json, README.txt
Commit, confirm Vercel deployment, and reopen Paddle League.

TEST:
With Paddle League closed, have Austin unfollow/re-follow to create a NEW
alert. Tap the NEW Lock Screen notification. It should open Austin's profile.
If not, verify in-app notification bell > Austin followed you navigates to his
profile, and confirm the deployed Vercel domain is paddle-league2.vercel.app.

STATUS: JavaScript syntax verified, iPhone behavior not yet tested.
