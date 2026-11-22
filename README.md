# MediReminder – Android app

A reminder tool only. It gives no medical advice and never replaces your doctor or pharmacist.

## Easiest: build the APK in the cloud (no Android Studio)
1. Create a free GitHub account and a new empty repository.
2. Upload everything in this folder to it (including the hidden `.github` folder).
3. Open the repository's **Actions** tab, choose **Build Android APK**, press **Run workflow**.
4. After about 5 minutes open the finished run and download **MediReminder-apk** (a zip holding `app-debug.apk`).
5. Copy the APK to your phone, tap it, and allow "Install unknown apps" when asked.
6. Open MediReminder and allow **Notifications** and, on Android 12 or newer, **Alarms & reminders**.

## Or build it on your computer
Needs: Node.js 20+ and Android Studio (includes the Android SDK).

    npm install
    npx cap add android
    npm run icons
    npx cap sync android
    npx cap open android

In Android Studio wait for Gradle to finish, plug in your phone (USB debugging on) and press Run,
or use Build > Build Bundle(s) / APK(s) > Build APK(s) and install the APK.

On first launch allow **Notifications**. On Android 12+ also allow **Alarms & reminders**
(Settings > Apps > MediReminder) so reminders arrive on time.

## How alerts work in the app
The app schedules a phone alarm-style notification for every dose in the next 7 days, so reminders
appear on the lock screen and over other apps even when MediReminder is closed. Open the app at
least once a week to schedule the next days. Marking Taken or Skip, snoozing, pausing, editing or
deleting a medicine updates the scheduled notifications automatically.

## Run as an installable web app instead
Upload the `www` folder to any HTTPS host and use "Add to Home Screen". Alerts then work only while
the app is open (web limits).

## Notes
- Data is stored on the phone only. No account, no sync between devices.
- Edit `www/index.html` to change the app, then run `npx cap sync android`.
