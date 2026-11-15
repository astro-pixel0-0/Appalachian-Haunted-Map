# Appalachia Anomalies — web/PWA

Free stack: Firebase Spark (Auth + Firestore, **no Storage needed** — photos are resized to ≤900px and stored in Firestore) + Firebase Hosting.

1. console.firebase.google.com → new project → Build → **Authentication** → Email/Password → enable. Build → **Firestore** → create (production mode).
2. Project settings → Add app → Web (</>) → copy the config into `config.js`.
3. Firestore → Rules → paste `firestore.rules` → Publish.
4. Host (pick one, all free):
   - Firebase Hosting: `npm i -g firebase-tools && firebase login && firebase init hosting` (public dir `.`, no SPA rewrite, keep existing files) → `firebase deploy`.
   - Or drag the folder into netlify.com/drop, or push to GitHub Pages.
5. Authentication → Settings → **Authorized domains** → add your hosting domain (Firebase's own *.web.app is already there).
6. On iPhone: Safari → Share → Add to Home Screen.

Moderation: new reports appear in the Firestore `reports` collection; delete offending docs in `sightings` / `photos` / `threads` yourself.
Limits: free Firestore ≈ 50k reads/day; OSM tiles are for light use only (the default map is USGS).

## Credits
- Interface sounds: "Pixelated UI" by Atelier Magicae (used under the creators' terms; the raw sound files are not distributed in this repository). Typing sound is synthesized in code.
- Map data: USGS The National Map, © OpenStreetMap contributors
- Weather: Open-Meteo.com
