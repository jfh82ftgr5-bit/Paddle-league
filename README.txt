PADDLE LEAGUE — NOTIFICATION ROUTING + TRAINING RECAP V3
November 7, 2026

BUILT ON THE WORKING V2 LOCK SCREEN PROFILE ROUTING

NEW: MATCH AND TOURNAMENT NOTIFICATION NAVIGATION
- Follower notification behavior is unchanged (verified on iPhone).
- Match-ready and score-confirmation notifications now look up the specific
  authorized match session, then open its ranked live/confirmation lobby.
- Tournament started/completed/match alerts try to open the specific
  tournament's existing bracket / spectator viewer.
- If a destination is unavailable, open the Matches screen with a message.
- Uses existing notification UUIDs, Supabase policies and OneSignal setup.
  No database, Edge Function, or service-worker changes.

NEW: TRAINING PRACTICE RECAP
- Training Progress now includes practice consistency by WEEK (not day),
  weeks active in the last eight, focus variety, most logged sport and focus.
- Rest days do not break a daily streak, because no daily streak is tracked.
- Derived only from existing private training logs; no new table or tracking.
- The existing weekly goals, calendar, and 8-week charts are preserved.

INSTALL (SAME 5 FILES METHOD):
1. Extract this ZIP.
2. Replace all 5 files in the root of your GitHub Paddle League repo on main:
   index.html, manifest.webmanifest, sw.js, vercel.json, README.txt
3. Commit and let Vercel deploy. Open the Home Screen app after deployment.

TEST:
A. Open Home > Your Training > Progress. Check Practice recap; log a sample
   practice only if you want, and check recap updates after saving.
B. In the in-app bell, tap a match or tournament notification if one exists.
   New Lock Screen alerts should use the same navigation after tapping.
C. Tap a new follower Lock Screen alert to confirm the V2 flow remains working.

NOTE: Only code syntax and non-live checks can be verified here. Actual match,
notification, and iPhone navigation behavior still need device testing.
Keep your working V2 backup in case you need to roll back.
