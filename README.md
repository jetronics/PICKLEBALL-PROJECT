# Open Play – Android APK

## Build the APK (no Android Studio needed)
1. Create a free account at github.com and a new **private** repository.
2. Upload everything in this folder (including the hidden `.github` folder) to the repo.
3. Open the repo → **Actions** tab → "Build Android APK" → it runs automatically (or press **Run workflow**).
4. When it finishes (about 5–8 minutes), open the run and download **open-play-apk** under Artifacts. Unzip it to get `app-debug.apk`.
5. Send the APK to your phone, tap it, and allow "Install unknown apps" when asked.

## Updating the app
Replace `www/index.html` with the new version, commit, and the workflow builds a fresh APK.

## Build on your own computer instead
Requires Node 20 and JDK 17 + Android SDK.

    npm install
    npx cap add android
    (add CAMERA permission to android/app/src/main/AndroidManifest.xml)
    npx cap sync android
    cd android && ./gradlew assembleDebug

APK: android/app/build/outputs/apk/debug/app-debug.apk
