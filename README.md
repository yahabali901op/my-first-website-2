# AnimeWorld Admin Movie Site

## Important
Only upload videos you created or have permission/license to distribute. This starter is a demonstration; review Firebase quotas, terms, and privacy requirements before launch.

## 1. Create Firebase project
1. Open https://console.firebase.google.com/ in Chrome.
2. Create a project.
3. Add a Web app and copy its config into `firebase.js`.
4. Enable Authentication > Sign-in method > Email/Password.
5. In Authentication, add your own admin user. Do not provide admin signup on the public site.
6. Copy that user's UID into `ADMIN_UID` in `firebase.js`.
7. Create a Firestore database.
8. Create a Storage bucket and check whether Storage is available on your Firebase plan/region.

## 2. Set secure rules
1. In Firestore > Rules, paste `firestore.rules`.
2. Replace `REPLACE_WITH_ADMIN_UID` with the same admin UID.
3. Publish the rules.
4. In Storage > Rules, paste `storage.rules`, replace the UID, and publish.

The public can read published movie records and video files. Only the configured admin UID can write movie records and upload/delete videos. Public video read is needed for streaming; do not upload private videos.

## 3. Configure firebase.js
Copy the Web app config values from Firebase Project settings > Your apps. Replace every placeholder and `ADMIN_UID`. The Firebase web config is not a secret; do not put service-account keys or private server credentials in this file.

## 4. Deploy on GitHub Pages from Android
1. Create a public repository called `anime-movie-site`.
2. Upload `index.html`, `admin.html`, `firebase.js`, `firestore.rules`, and `storage.rules` to the repository root. (The two `.rules` files are reference copies; Firebase rules must also be published in Firebase Console.)
3. Commit changes.
4. Repository Settings > Pages > Deploy from a branch > `main` > `/(root)` > Save.
5. Wait for deployment.
6. Open `https://YOUR-USERNAME.github.io/anime-movie-site/`.
7. Admin panel: `https://YOUR-USERNAME.github.io/anime-movie-site/admin.html`.

## Notes and limitations
- The 500 MB browser-side limit in admin.html is a starter guard, not a guarantee that the Firebase plan will accept files that large. Check current quotas and use resumable uploads.
- Firebase Storage pricing/eligibility may vary; verify current plan before relying on free hosting.
- Direct Firebase download URLs may be shareable by anyone who has them. Public video playback is intentionally enabled here.
- This uses Firebase client SDK from a CDN and needs an internet connection.
- This is a starter project; consider App Check, upload moderation, file validation, and a more robust backend for a production service.
