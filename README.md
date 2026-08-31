# Sehat — Doctor App (Demo)

Professional dark glassmorphism UI demo for a doctor/healthcare booking app.

## 1. Install as a PWA (no APK needed)
Open `www/index.html` on a web server (e.g. via GitHub Pages) in Chrome on Android:
- Chrome menu → **Install app** / **Add to Home screen**
- The app installs like a native app (its own icon, full-screen, offline-capable via the service worker).

## 2. Get a real Android APK
This repo has a GitHub Actions workflow (`.github/workflows/build-apk.yml`) that wraps the web app
with [Capacitor](https://capacitorjs.com) and builds a real `.apk`.

**How to get the APK:**
1. Go to the **Actions** tab of this repository.
2. Open the latest **Build Android APK** run (it runs automatically on every push to `main`, or click **Run workflow** to trigger it manually).
3. When it finishes, download the **sehat-doctor-app-debug-apk** artifact.
4. Transfer the `.apk` to an Android phone and install it (enable **Install unknown apps** for the browser/file manager you use).

This is a **debug build** (unsigned) — fine for testing/sideloading. For a Play Store release, the APK/AAB
needs to be signed with a release keystore.

## Project structure
- `www/` — the actual web app (HTML/CSS/JS), PWA manifest, service worker, icons
- `capacitor.config.json` — tells Capacitor to wrap `www/` into a native Android project
- `.github/workflows/build-apk.yml` — CI that builds the APK on every push
