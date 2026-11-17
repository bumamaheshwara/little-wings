# Little Wings – Teacher App

A mobile app for Little Wings Play School teachers to register students, keep full profiles and download PDFs (admission application, ID card, parent meeting report).

**App address:** https://bumamaheshwara.github.io/little-wings/

- Free hosting on GitHub Pages and a free Firebase database (Spark plan).
- Teachers sign in with Google. Only people approved by an Admin can see student records.
- The **first person to sign in becomes Admin**, so sign in yourself first.

---

## Setup (about 15 minutes, one time)

### 1. Create the Firebase project
1. Go to https://console.firebase.google.com and click **Add project** (Create a project). Name it `little-wings` and turn Google Analytics off.
2. **Build → Authentication → Get started → Google → Enable**. Pick your support email and click **Save**.
3. Still in Authentication, open **Settings → Authorized domains → Add domain** and add `bumamaheshwara.github.io`.
4. **Build → Firestore Database → Create database**. Choose location **asia-south1 (Mumbai)** and **Start in production mode**.
5. In Firestore, open the **Rules** tab. Delete what's there, paste the whole contents of `firestore.rules` and click **Publish**.
6. Click the ⚙️ gear → **Project settings**. Under **Your apps**, click the **</>** (Web) icon, name it `Little Wings` and click **Register app**. Firebase shows a `firebaseConfig = { ... }` block. Keep that page open.

### 2. Put the app on GitHub
1. Sign in at https://github.com as **bumamaheshwara**.
2. Click **+ → New repository**. Name it `little-wings`, set it to **Public** and click **Create repository**.
3. Click **uploading an existing file**. Drag in **all the files from this folder**, then click **Commit changes**.
4. In the repository, open `config.js`, click the ✏️ pencil and replace each `PASTE_...` value with the matching value from step 1.6. Click **Commit changes**.
5. Go to **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then click **Save**.
6. Wait 1–2 minutes, then open **https://bumamaheshwara.github.io/little-wings/**.

### 3. First sign-in
1. Open the app and tap **Sign in with Google**. You become the **Admin**.
2. Open **Teachers** and fill in **School details** (address, phone, academic year). These print on every PDF.
3. Add your **Class teachers** (used to assign students).
4. Tap **Copy app link** and send it to your teachers on WhatsApp.
5. Each teacher signs in once and sees "Waiting for approval". Open **Teachers → App access** and tap **Approve**. Use the dropdown to make management staff **Admin**.

### Install on phones
- **Android (Chrome):** open the link, tap ⋮ → **Add to Home screen** (or **Install app**).
- **iPhone (Safari):** open the link, tap Share → **Add to Home Screen**.

---

## Who can do what
| | Teacher | Admin (management) |
|---|---|---|
| Dashboard, students, profiles | ✅ | ✅ |
| Register / edit students, likes, learning, progress, activities, notes | ✅ | ✅ |
| Download application, ID card, parent report PDFs | ✅ | ✅ |
| Delete students | – | ✅ |
| Approve / remove teachers, change roles | – | ✅ |
| Class teacher list, school details | view | ✅ |

## Files
- `index.html`: the whole app
- `config.js`: your Firebase settings (the only file you edit)
- `firestore.rules`: security rules to paste into Firebase
- `manifest.json`, `icon-192.png`, `icon-512.png`: home-screen app icon

## Good to know
- The Firebase free plan covers 1 GiB of data, 50,000 reads and 20,000 writes per day, which is plenty for a play school.
- The values in `config.js` are not passwords, so a public repository is fine. Student data lives only in Firebase, behind sign-in and the security rules.
- Type names in English letters. The PDFs can't show Telugu or Hindi script.
- **Troubleshooting:** if sign-in shows "This web address is not allowed yet", repeat step 1.3.
