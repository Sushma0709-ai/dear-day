# Dear Day — build it as a real Android app

This turns the web app into an actual installable `.apk`, with reminders
scheduled through Android's own alarm system — so they fire even if the
app is fully closed and the phone has been sitting idle.

You'll need, on your computer:
- Node.js (from nodejs.org) — anything v18 or newer
- Android Studio (from developer.android.com/studio) — free

## 1. Install dependencies

Open a terminal in this folder (`dear-day-native`) and run:

```
npm install
```

## 2. Add the Android platform

```
npx cap add android
```

This creates an `android/` folder — the actual native project.

## 3. Sync your web app into it

```
npx cap sync android
```

Run this again any time you change files in `www/`.

## 4. Open it in Android Studio

```
npx cap open android
```

Android Studio will open the project and download the Gradle build
tools the first time — that can take a few minutes.

## 5. Run it on your phone

- Plug your Android phone in by USB, with **USB debugging** turned on
  (Settings → About phone → tap "Build number" 7 times → Developer
  options → USB debugging).
- In Android Studio, pick your phone from the device dropdown at the
  top and press the green ▶ Run button.
- The app installs and opens on your phone directly.

## 6. Get a real .apk file to keep or share

In Android Studio: **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.
When it finishes, click "locate" in the notification to find the
`.apk` file — you can send that to your phone and install it anytime,
no cable needed (you may need to allow "install unknown apps" for
whichever app you use to open it).

## 7. First launch on your phone

Tap "Turn on alerts" in the app once — Android will ask for
notification permission. Grant it, and every task with a time gets a
real scheduled system notification, independent of the app staying
open.

## Publishing to the Play Store (optional, later)

If you ever want it on the Play Store for real, you'll need a
$25 one-time Google Play developer account, and Android Studio can
generate a signed release bundle (**Build → Generate Signed Bundle**).
Happy to walk through that when you're ready — no need to think about
it now.
