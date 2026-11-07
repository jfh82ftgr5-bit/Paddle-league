PADDLE LEAGUE — MATCH RECOVERY V4
November 7, 2026

FIX: Active match sessions reappear when Paddle League is closed or the phone is restarted.
- Matches page shows Unfinished Matches with a Resume button.
- Automatically reopens the latest unfinished match in the current club in the Matches screen without redirecting away from Home.
- Works for both ranked and casual sessions, including preexisting unfinished matches; scored/official matches remain in History.
- Match codes are retrieved from a signed-in user's own participant records. No scores, match state, ELO, notifications, or OneSignal configuration were changed.

DATABASE: The safe, read-only RPC list_my_active_matches_v1 was added to the connected Supabase production project already. Do NOT run migrations manually. It returns only the signed-in player's unfinished matches (waiting, live, awaiting_confirmation), up to 20 from the last 90 days, and cannot be called anonymously.

INSTALL:
Replace these same 5 files in the GitHub Paddle-league repo root, branch main:
  index.html
  manifest.webmanifest
  sw.js
  vercel.json
  README.txt
Commit changes and wait for Vercel deployment. Reload Home Screen app.

TEST:
1. Open Matches and confirm Unfinished Matches displays the old game if it still has an active status. Tap Resume.
2. Create or join a NEW unranked/casual 1v1 match for testing; do not enter scores.
3. Close Paddle League completely and reopen it, go to Matches. Verify lobby and same match code are still there.
4. Have the other player refresh/resume their lobby to verify both see the same players and status.
5. Finish the match with actual scores only when ready; official matches should disappear from Unfinished Matches and remain in History.

LIMIT: Browser JavaScript syntax and mocked recovery behavior were checked, but a two-phone live end-to-end test remains pending.
