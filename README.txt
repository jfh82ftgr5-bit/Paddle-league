PADDLE LEAGUE — ACCOUNT DELETION V2 (BETA)

This update continues directly from the App Store Safety V1 build and preserves Training Sessions and Progress Dashboard V2, player blocking, and existing competitive features.

INSTALL (same 5-file method):
Upload/replace these five files in GitHub repo Paddle-league, branch main:
  index.html
  manifest.webmanifest
  sw.js
  vercel.json
  README.txt
Wait until Vercel finishes deploying. Do not upload the entire ZIP as one file to GitHub.

ALREADY DEPLOYED TO SUPABASE — DO NOT RUN EXTRA SQL:
- Edge Function delete-paddle-account (requires signed-in user's JWT and explicit confirmation)
- Shared history protection: authenticated user deletion is prevented when club ownership, matches, tournament states, game-night records or other shared game history would be affected.
- Existing account_deletion_requests is still used to track unfinished deletion requests.

WHAT HAPPENS IF A PLAYER REQUESTS DELETION:
- No shared history: the signed-in user confirms, the server deletes that Supabase Auth user, and on-delete cascading removes their personal account records, posts and training logs.
- Shared history: the server stores a pending deletion request. The account stays active, and an administrator must review how to preserve the other players' historical data before completing deletion. Players can cancel a pending request.

IMPORTANT BETA LIMITATION:
This is NOT the complete automated deletion system for established players with shared history. Requests in that case currently require human follow-up by the app owner; there is no automatic staff queue/notification or promised completion time. Before App Store submission, define and implement a reliable request handling process, user completion notices, privacy policy/retention rules, and a safe de-identification pathway for shared historical records.

DO NOT TEST THE DELETION BUTTON WITH YOUR MAIN ACCOUNT.
It could permanently delete that account if no shared history is present. For tests, use a newly created disposable test account with NO activity, and only if you are willing to lose that account.

TESTING DONE BY ASSISTANT:
- Frontend JavaScript syntax check passed.
- Simulated response handling tested for queued and deleted statuses and pending status display.
- Supabase Edge Function deployment verified, and DB guard function/trigger and security settings checked.
- No real users or records were deleted to test this feature; production end-to-end deletion still needs validation with an expendable test account.
