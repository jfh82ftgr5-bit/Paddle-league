PADDLE LEAGUE — PRIVACY & SUPPORT V1
October 29, 2026

INSTALL: Replace these five files at the root of the Paddle-league GitHub repo (main branch), then wait for Vercel auto-deploy.

FILES
- index.html: Privacy & Support cards on Account page; support request form/history, public Privacy Policy and Support Center.
- manifest.webmanifest
- sw.js
- vercel.json (SPA rewrite preserves /privacy and /support)
- README.txt

PUBLIC URLS after deployment:
https://paddle-league2.vercel.app/privacy
https://paddle-league2.vercel.app/support

IN-APP: Account > Privacy & Support. Signed-in users can submit support tickets.
The support_tickets database and restricted submit_support_ticket function are already installed in Supabase. Admin must check Supabase support_tickets for incoming reports.

IMPORTANT BEFORE APP STORE SUBMISSION:
- Have a parent/guardian or responsible adult create a dedicated public support email; publish verified contact information on the support page. Do NOT publicly post a personal address/phone.
- Review and finalize the beta privacy policy with the legal account holder and validate actual data practices, retention, age eligibility, and Apple's privacy nutrition labels.
- Test the support form, public links, and all app features.
- Account deletion with shared histories still requires a real administrator workflow.

TEST: Deploy; open Account; verify privacy link/support form; sign out and open /privacy and /support on Safari; submit ONE test support ticket (no sensitive details); confirm it appears in Supabase support_tickets.
