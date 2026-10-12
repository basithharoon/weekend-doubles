# Weekend Doubles

A scorebook for our weekend badminton doubles. It tracks standings, which duos win most, guests, and suggests fair teams.

It's one static page (`index.html`) hosted on GitHub Pages. Scores are stored in Firebase Firestore so everyone sees the same data live.

## One-time Firebase setup

1. Go to https://console.firebase.google.com and click **Create a project** (Google Analytics isn't needed).
2. In the project, open **Build → Firestore Database → Create database**. Pick a location near you and start in **production mode**.
3. Open the **Rules** tab, replace everything with the contents of [`firestore.rules`](firestore.rules), and click **Publish**.
4. Open **Project settings** (gear icon) → **Your apps** → click the **Web** icon (`</>`), give it a name, and register it. Don't tick Firebase Hosting.
5. Copy the `firebaseConfig` object it shows and paste it into [`firebase-config.js`](firebase-config.js), replacing `null`:

   ```js
   export const firebaseConfig = {
     apiKey: "...",
     authDomain: "...",
     projectId: "...",
     storageBucket: "...",
     messagingSenderId: "...",
     appId: "..."
   };
   ```

6. Commit and push. GitHub Pages updates in a minute or so.

## Note

There's no login, so anyone with the link can add or delete games. That's fine for a group of friends; just don't post the link publicly.
