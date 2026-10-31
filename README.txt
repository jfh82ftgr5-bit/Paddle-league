PADDLE LEAGUE — CROSS-CLUB OPEN TOURNAMENTS V1
October 30, 2026

INSTALL ON IPHONE:
Replace the same 5 files in the GitHub Paddle-league repo root, branch main:
  index.html
  manifest.webmanifest
  sw.js
  vercel.json
  README.txt
Commit the changes; Vercel deploys automatically. Refresh Paddle League on both devices.

DATABASE: The two new Supabase migrations for public tournament registration and cross-club tournament results have ALREADY been applied to the connected production database. Do not run SQL manually.

WHAT'S NEW:
- A club owner/admin can choose "Open — players from any club can join" when creating a tournament.
- Open tournaments start in registration status; any signed-in active player who belongs to any club can register without joining the host club.
- Under Matches > Tournaments, open tournaments hosted by other clubs are visible to registered users, with Join, Leave and registration counts.
- An organizer starts the bracket after at least two players have registered. Participants are seeded by global ELO; single, double and round-robin brackets reuse the existing tournament engine.
- Club-only preselected-player tournaments remain available, and previous tournaments retain their settings.
- The backend accepts a verified entrant from another club when the organizer enters official scores, preserving ranked vs unranked behavior.
- Match results should appear in players' global match history.

SAFE TEST:
1. Switch to a club you own or administer (e.g., Paddle players).
2. Create Tournament > Who can enter? > Open, Unranked, max 4, choose format Single Elimination.
3. Join your own tournament, then ask someone in a different club to refresh Matches and Join Tournament.
4. After at least 2 register, organizer taps Start Bracket.
5. Enter a test score, check advancement and both players' histories. Unranked tournament results still affect W/L and streak, but do NOT change ELO.

NOTE: No end-to-end two-account tournament test has been completed yet. Do not treat this as App Store release-ready until that test and security audit pass.
