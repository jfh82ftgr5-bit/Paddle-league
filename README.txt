Paddle League — Moderation V1

NEW:
- Server-side filtering for clearly inappropriate display names, posts, and comments
- Existing inappropriate display names are automatically replaced with Anonymous Player ####
- Affected users get a popup explaining what happened the next time they open the app
- Users can immediately choose a new appropriate display name
- Report buttons for posts, comments, and display names
- Club owners get a Club Moderation queue in Account
- Club owner actions: remove content/reset reported name, mute for 24 hours, or dismiss report
- Muted users cannot post/comment in that club until the mute ends
- Filtering is enforced by Supabase, not only by the webpage

PRESERVED:
- Global League + Global Leaderboard
- Clubs
- Rally starting rank / 800 ELO
- Courts
- Matches + Tournaments combined into one tab
- Tournament V3.1 features

UPLOAD:
Upload/replace all 5 files in the root of the GitHub Paddle-league repository and commit to main. Vercel should redeploy automatically.

SUPABASE:
Moderation V1 backend changes have already been applied. No SQL/dashboard work is needed.
