PADDLE LEAGUE — PROGRESS DASHBOARD V2

Upload/replace these same 5 files in GitHub repo root:
1. index.html
2. manifest.webmanifest
3. sw.js
4. vercel.json
5. README.txt

NEW (builds on working Training Sessions V1):
- Training Progress screen linked from Home and Account.
- Optional weekly goals (sessions and minutes), with private Supabase sync.
- Monthly training activity calendar with tappable dates.
- Last eight weeks of practice: court time / session-count chart.
- Goals and charts refresh after adding, editing, or deleting a practice.
- Clear goals without deleting saved sessions.
- Training remains private; ELO, matches, seasons, ranks, tournaments unaffected.

SUPABASE: New `training_goals` table with per-user Row Level Security was applied to the existing project.
Existing `training_sessions` records are reused. No manual SQL necessary.

TEST:
1. Deploy the five files to GitHub main (Vercel redeploys).
2. Open Home > Your Training > Progress.
3. Set a modest weekly goal and save, reopen, and verify it persists.
4. Check current month's calendar and past 8-week chart.
5. Log/edit a practice, verify progress changes; try clearing goals (session remains).

All other app files/features remain unchanged.


APP STORE SAFETY V1 (BETA)
- Player profiles now offer a Block action; blocked players can be managed from Account > Safety & Privacy.
- Blocking removes mutual follows, hides social posts/comments/reactions, and prevents new follows and Looking to Play connections. Match results/rankings remain public.
- Account now has Request Account Deletion. This creates a review request ONLY and does not automatically remove the user or historical data. Manual processing and complete account deletion automation are still outstanding before App Store submission.
- Supabase migration was applied directly. Do not run SQL from this ZIP.
- This remains a beta requiring testing across different real player accounts.
