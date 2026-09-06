Paddle League — Bottom Navigation Fix

WHAT THIS FIXES
- Bottom navigation no longer uses iOS Safari window-fixed positioning.
- The app now scrolls inside its own viewport while the nav stays anchored at the bottom.
- This prevents the bottom bar from jumping/moving when Safari's browser controls expand or collapse.

ALSO INCLUDED
- Dynamic rank-scaled ELO
- Players Near Your ELO
- Double-elimination Championship / Reset Final
- Proper Champion declaration

UPLOAD THESE 5 FILES TO THE ROOT OF THE GITHUB REPO:
1. index.html
2. manifest.webmanifest
3. sw.js
4. vercel.json
5. README.txt

Commit to main and let Vercel redeploy.
