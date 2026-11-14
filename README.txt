# MG Attendance PWA wrapper

This package is a starter PWA shell for your existing Google Apps Script web app.

## Files
- `index.html` — mobile wrapper that embeds your current Apps Script deployment
- `manifest.webmanifest` — PWA name, display mode and icons
- `service-worker.js` — caches only the wrapper shell, never attendance data
- `icons/` — generated MG Attendance app icons

## Publish on GitHub Pages
1. Sign in to GitHub and create a **public** repository, for example `mg-attendance-app`.
2. Upload all files and folders from this package to the repository root (not the ZIP file itself).
3. Open repository **Settings → Pages**.
4. Under Build and deployment, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then Save.
6. Wait for GitHub Pages to publish. Your address will look like `https://YOUR-USERNAME.github.io/mg-attendance-app/`.

## Install on Android
1. Open the published GitHub Pages address in Chrome.
2. Wait for it to load, then use Chrome menu → Install app (or Add to Home screen).

## Install on iPhone
1. Open the published GitHub Pages address in Safari.
2. Tap Share → Add to Home Screen.
3. If shown, enable Open as Web App, then tap Add.

## Important limitations and security
- The wrapper embeds the Apps Script URL supplied by you. If Google redirects to a sign-in page, blocks the frame, or some feature does not work in an embedded browser, use the **Open directly** link in the wrapper. The direct Apps Script URL remains available.
- `ALLOWALL` permits any website to frame your Apps Script page. Google explicitly warns developers to implement clickjacking protection when using it. Only keep this setting if embedding is needed and you understand the risk.
- Your deployment is currently set to **Anyone**. That can expose the web app to anyone who obtains the URL, depending on the app's own authentication and data checks. Do not store or display sensitive attendance information without appropriate authorization.
- The service worker caches only static wrapper files. It does not make attendance data available offline.
- This is a PWA wrapper, not a native APK or App Store app. iPhone users install it from Safari's Share menu; Android users install it from Chrome.
- Test all attendance actions on both devices before relying on it for production.

## Your current Apps Script URL
https://script.google.com/macros/s/AKfycbwv3nJxDrN-qWcUKPo_Ya0xgyck3duI2-qwNX-FzlfZllL1v6l8AK0sDHYXzLDT7tVk/exec
