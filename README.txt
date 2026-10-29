PADDLE LEAGUE — TRAINING SESSIONS V1

Upload/replace the usual FIVE files in the GitHub repo root:
1. index.html
2. manifest.webmanifest
3. sw.js
4. vercel.json
5. README.txt

NEW — TRAINING SESSIONS V1
- Home now features Your Training first, with a weekly activity chart, session count, and court time.
- Log Activity from Home: sport, session type, duration, date, training focus, and optional notes.
- Private training history with Edit and Delete.
- My Training Log shortcut in Account.
- Compatible with the existing public.training_sessions Supabase table; no new SQL migration needed.
- Sessions are owned and accessible only by the signed-in user under existing RLS rules.
- Training does NOT change global ELO, wins/losses, seasons, ranked match history, or tournaments.

IMPORTANT: Share-to-club and public training feed are NOT included in V1; all training sessions remain private.
The weekly dashboard reports manually logged sessions only, not official competitive matches.

FEATURES PRESERVED
- Home Polish V1.1, League Polish V1, Clubs Polish V1
- Game Night V1.1, ranked/casual matches, tournaments, courts, court leaderboards
- Looking to Play, season tracking, achievements, milestones, and notifications

DEPLOYMENT
- The existing Supabase project must be ACTIVE_HEALTHY.
- Keep your current icon-192.png and icon-512.png in the repo; these are not replaced.
- If the page appears unchanged after deployment, refresh the installed app or reopen the browser page.
