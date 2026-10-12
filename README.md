# Eldorado — GitHub Pages + Firebase

The supplied `index.html` already initializes Firebase for project `eldorado-82c5e` and saves notes/books to Cloud Firestore. Image files are uploaded to Firebase Storage and image metadata is saved in Firestore.

## Before publishing
1. In Firebase Console, open project `eldorado-82c5e`.
2. Enable Firebase Authentication → Email/Password.
3. Create/verify the app's owner account in Authentication. The HTML has a default app login (`fasly` / `8820`); this is an app-level default and is not a secure production credential. Change it before sharing publicly.
4. Confirm Firestore Database exists and that rules permit authenticated users to read/write only the documents they are allowed to access.
5. In Storage, create/enable the bucket and set secure Storage rules for authenticated users. Do not use public read/write rules.
6. Check Firebase project settings that the exact GitHub Pages domain is authorized under Authentication → Settings → Authorized domains.

## Publish on GitHub Pages
1. Create/open a GitHub repository.
2. Upload `index.html` to the repository root.
3. Go to Settings → Pages.
4. Choose “Deploy from a branch”, select `main` and `/(root)`, then Save.
5. Wait for the Pages URL to appear and open it over HTTPS.
6. Test note creation, reload the page, and confirm the note remains. Upload an image and confirm it remains after reload and on another device.

## Important
Publishing the HTML does not configure Firebase rules or grant access to the GitHub repository. The Firebase web config is client-side by design; security must be enforced by Firebase Authentication, Firestore rules, and Storage rules. The app's default login values are embedded in client-side code and should not be treated as secure authentication.
