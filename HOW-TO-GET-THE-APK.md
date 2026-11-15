# E-Saud: get the APK

## Easiest: build it in the cloud (no Android Studio)
1. Make a free account at github.com and create a new repository (any name).
2. Upload everything in this folder to it, including the hidden `.github` folder.
   (On a computer: unzip, then drag all the files and folders into the repository page.
    The phone browser often can't upload folders, so use a computer or "Desktop site" mode.)
3. Open the repository's **Actions** tab. A run called "Build Android APK" starts by itself.
   If not, click it and press **Run workflow**.
4. After about 5-8 minutes, open the finished run and download **E-Saud-APK** at the bottom.
   Unzip it to get `app-debug.apk`.
5. Send the APK to your phone, tap it, and allow "Install unknown apps" when asked.

## Or on your own computer
Install Node.js 18+, Java 17 and Android Studio, then in this folder run:

    npm install
    npx cap add android
    npx capacitor-assets generate --android
    npx cap sync android
    cd android && ./gradlew assembleDebug

The APK is at `android/app/build/outputs/apk/debug/app-debug.apk`.

## No-build option
Host the `www` folder (Netlify Drop, GitHub Pages) and open the link in Chrome on Android,
then menu -> Add to Home screen. It installs like an app. You can also paste the link into
pwabuilder.com to make an APK.

## Notes
- The APK is a "debug" build: fine for installing and sharing directly, not for Google Play.
  For Play Store you need a signed release build and a $25 developer account.
- Data (accounts, orders, products) is stored only on each phone.
