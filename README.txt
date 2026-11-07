PADDLE LEAGUE — 24-HOUR WAITING LOBBIES + CLEAN MATCH VIEW V5
November 7, 2026

Changes:
- Waiting ranked and casual match lobbies are automatically marked CANCELLED after 24 hours, checked every 15 minutes.
- LIVE and AWAITING_CONFIRMATION matches are never automatically expired.
- No ELO, rank, score or completed match records are changed by expiration.
- Matches page now shows one primary unfinished match, other unfinished matches hidden in an expandable section.
- Creators can CANCEL a waiting match manually from the lobby or the Unfinished Matches card.
- Old waiting rooms (already older than 24 hours) are filtered from V5 immediately and automatically cancelled by the scheduled job.
- Keeps previous training, notifications, follower deep linking and other features.

PRODUCTION SUPABASE: Applied migrations already, including read RPC list_my_active_matches_v2,
creator-only cancel RPC cancel_my_waiting_match_v1, expire_waiting_match_sessions_v1 and scheduled job
paddle-waiting-match-expiry-v5. Do NOT run SQL manually.

INSTALL (same 5-file method): Replace exactly these files in the Paddle-league repo root on GitHub main:
index.html, manifest.webmanifest, sw.js, vercel.json, README.txt
Commit and let Vercel deploy. Refresh home-screen Paddle League on both iPhones.

TEST:
1. Create one CASUAL 1v1 lobby. Current Match should appear, and creator should see Cancel.
2. Close/reopen app, and verify the match lobby can still be resumed.
3. Cancel that waiting lobby. It should disappear from the unfinished section; no ELO change.
4. LIVE/awaiting-confirmation matches should remain resumeable after restart.
5. After 24 hours, waiting lobbies vanish from the unfinished list; cron checks every 15 minutes.

Note: JS syntax is checked, but end-to-end manual two-device testing is still needed.
