# Task Life

A goal and performance tracker: set goals like "Gym at least 2 days a week" or "Cake at most 1 day a week", tick off each day, and see the percentage of weeks you hit your target (overall, last 4 weeks, or this week), with a weekly chart and streaks. Data is stored on the phone only.

## Get the APK (no Android Studio needed)

1. Create a free GitHub account and a new **private** repository.
2. Upload everything in this folder (keep the `.github` folder).
3. Open the repo's **Actions** tab, choose **Build Android APK**, click **Run workflow**.
4. After 4–6 minutes open the finished run and download the **task-life-apk** artifact (a zip containing `app-debug.apk`).
5. Send the APK to your phone, open it, and allow "Install unknown apps" when asked.

## Build it yourself instead

Requires Node 20, JDK 17 and the Android SDK:

```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```

APK: `android/app/build/outputs/apk/debug/app-debug.apk`

## Quick option without an APK

Host the `www/` folder on any HTTPS host (Netlify, GitHub Pages, Cloudflare Pages), open it in Chrome on Android and choose **Add to Home screen → Install**. It works offline.

## Files

- `www/` – the app (single `index.html`, no dependencies)
- `capacitor.config.json` – Android wrapper settings (app id `com.taskslife.performance`)
- `.github/workflows/build-apk.yml` – cloud APK build
