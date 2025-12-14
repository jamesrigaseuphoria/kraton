
# Firebase Sync Setup

1) Go to https://console.firebase.google.com → Add project.
2) Enable **Firestore** (Production mode).
3) Enable **Authentication → Anonymous**.
4) Copy your **firebaseConfig** from Project settings → Web app.
5) In `index.html`, replace the placeholders in `firebaseConfig`.
6) (Optional) Firestore Rules (basic):
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /app/{docId} {
      allow read: if true;
      allow write: if request.auth != null;
    }
  }
}
```
7) Upload `index.html` to your GitHub Pages repo (root). Open your site URL.
