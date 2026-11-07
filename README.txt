PADDLE LEAGUE — FOLLOWER PUSH TAP NAVIGATION V1
November 7, 2026

CHANGES:
- Keeps the existing OneSignal push configuration and service worker unchanged.
- Captures OneSignal notification clicks and waits until the signed-in session and clubs load.
- Resolves the tapped alert against the signed-in user’s in-app notifications.
- Reuses the existing openNotification() behavior, including opening follower profiles.
- If the tapped alert cannot be matched safely, opens the notification inbox instead of guessing.

INSTALL (same 5-file workflow):
1. Replace these 5 files in the Paddle League GitHub repo root on main:
   index.html, manifest.webmanifest, sw.js, vercel.json, README.txt
2. Commit and allow Vercel to deploy. Reopen the Home Screen app.
3. Keep push notifications enabled (do not unsubscribe/reinstall).

TEST:
1. With Paddle League closed, have Austin trigger a new follower notification.
2. Tap it on the iPhone Lock Screen.
3. Check whether Austin's profile opens. If not, see whether the in-app notification inbox opens.
4. Also tap the follower alert in the in-app notification bell to verify the existing route.

LIMITATION: The notification-sending Supabase Edge Function is not included in
these 5 files. Tap navigation works when the OneSignal click event includes
matching notification metadata or a uniquely matching title/body. If the event
is not delivered or cannot be matched on cold launch, the server-side push
payload may also need a URL and notification_id/entity_id. Not verified on-device.
No database migrations are required for this frontend change.
