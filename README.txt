PADDLE LEAGUE — ADMIN SUPPORT INBOX V1
October 29, 2026

INSTALL: Replace the same five files in the Paddle-league GitHub repository root on branch main. Vercel redeploys automatically.

FILES: index.html, manifest.webmanifest, sw.js, vercel.json, README.txt

NEW FEATURE: Under Account > Privacy & Support, an Admin Support Inbox appears ONLY for a designated support administrator. Review up to 100 recent tickets, filter by status, search by subject/category, expand to see messages and contact email, and save status Open, Reviewing, or Closed. Status changes appear in the sender's Support History.

SECURITY: Support admin membership is managed in Supabase public.support_admins (not by display name or club ownership). Exactly one existing account was granted access, based on the previously confirmed beta test ticket. No client permission to add administrators. Ticket privacy is enforced by RLS; status updates are applied by the restricted Supabase RPC support_admin_set_ticket_status.

TEST:
1) Upload all 5 files to GitHub, open Paddle League, Account > Privacy & Support.
2) Admin Support Inbox should appear below Contact Support. There should be 1 open ticket marked 'Test'.
3) Expand it, choose Reviewing, Save status. Confirm the counters and your own Support History update.
4) Open in another player's account; admin card should NOT appear and the backend must deny reading other players' tickets.

LIMITS: Inbox handles status only, not reply emails. It currently shows the latest 100 tickets and requires manual refresh. Admins must handle sensitive requests carefully. No actual emails are sent by changing status.


ACCOUNT DELETION V3 (2026-10-29)
- Privacy & Support and Admin Support Inbox are preserved.
- Account > Safety & Privacy > Account Deletion now has a non-destructive Check deletion readiness control.
- Server: delete-paddle-account Edge Function v2 deployed separately, with protected Supabase deletion logic.
- Database: anonymous historical player profiles preserve other players' match scores; the authenticated account and private content are removed on completed deletion.
- Club owners and people in active events are blocked from automatic deletion until safely resolved.
- CRITICAL: Do not test actual deletion on your primary account. No live deletion has been tested yet. Test only with a disposable account that has explicitly consented to permanent removal.
- App Store launch still requires full deletion testing, administrator processing of blocked requests, security review, and legal/privacy review of retained match records.
