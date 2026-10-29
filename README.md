# Rx Qatar Zone — Android-friendly tournament app prototype

This is a responsive, installable web app prototype designed to be tested on an Android phone and wrapped by a compatible online WebView-to-APK builder.

## Included now
- Responsive home screen and Rx Qatar Zone branding
- Sample BR Solo, BR Duo, BR Squad, CS 1v1 and CS 4v4 tournament cards
- Filters, demo registration, numeric UID validation
- Demo wallet with minimum deposit ৳20, minimum withdrawal request ৳100 and sample ৳5 fee
- Transaction list, player profile form, match list, notifications placeholder and tournament rules
- PWA manifest and app icon

## Important limitations
- This is a **front-end prototype**, not a production tournament platform.
- Demo wallet entries are local page-session data only. No money is transferred, no payment is verified, and no actual withdrawal is sent.
- Google sign-in, database persistence, admin authentication, room management, live leaderboards, anti-cheat evidence workflow and payment-provider integration are not configured.
- Paid entry and cash-prize tournaments may be subject to local laws, game publisher rules and payment-provider policies. Obtain appropriate legal/provider approval before enabling real-money features.
- Use of Free Fire names/assets should follow the publisher's brand and tournament policies. This project is not affiliated with or endorsed by Garena.

## Run locally on phone or computer
Open `index.html` in a browser, or upload the project to GitHub and enable GitHub Pages.

## GitHub Pages (mobile browser)
1. Sign in to GitHub and create a new repository, for example `rx-qatar-zone`.
2. Upload all files and folders from this ZIP. Keep `index.html`, `style.css`, `app.js` and `manifest.json` at the repository root.
3. In repository **Settings → Pages**, select **Deploy from a branch**, choose `main` and `/ (root)`, then Save.
4. Wait for GitHub Pages to publish the site. Open the URL shown in Pages settings.
5. Test every screen on your phone before wrapping it as an APK.

## APK wrapping
1. Use an online builder that explicitly supports packaging your own HTTPS website as an Android WebView APK.
2. Enter the published GitHub Pages URL and app name `Rx Qatar Zone`.
3. Set package ID to a unique reverse-domain identifier you control, e.g. `com.example.rxqatarzone` only for testing. Replace `example` with a domain/namespace you own before public release.
4. Add the supplied icon if the builder supports custom icons, then build and test the APK.
5. Do not provide payment secrets, Firebase service-account keys or private API keys inside front-end files.

## Recommended production architecture
- Frontend: this web app or a React/Vite app
- Authentication: Firebase Authentication (Google provider) with authorized domains
- Database: Firebase Firestore or a secured backend database
- Server functions: verify tournament joins, results, wallet ledger and admin actions server-side
- Admin: separate role-protected dashboard; never rely on a hidden button as security
- Payments: approved merchant/API integration with server-side verification, idempotency, audit logs and withdrawal review
- Security: database rules, rate limits, validation, anti-fraud checks, backups and privacy policy

## Suggested next milestones
1. Publish this prototype to GitHub Pages.
2. Add Firebase project configuration and Google sign-in.
3. Add database collections for players, tournaments, registrations, match results, notices and wallet ledger.
4. Build a protected admin dashboard.
5. Only after legal and payment-provider review, integrate approved payment APIs.
