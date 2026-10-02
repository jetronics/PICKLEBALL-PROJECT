# WataPickle Matcher – Android APK

## Build the APK (no Android Studio needed)
1. Create a new GitHub repository (private is fine).
2. Upload everything in this folder, including the hidden `.github` folder.
   Check that `.github/workflows/build-apk.yml` is in the repo.
3. Open the repo -> **Actions** -> "Build Android APK" (runs automatically, or press **Run workflow**).
4. After about 5-8 minutes, download **watapickle-apk** under Artifacts and unzip it to get `WataPickle-buildN.apk`.
5. Send it to your phone, tap it, and allow "Install unknown apps".

## Updating the app
Replace `www/index.html` (and `icon.png` if the logo changes), commit, and a new APK is built.

## Notes
- The launcher icon is made from `icon.png` by `make_icons.py` during the build.
- The app name on the phone is set in `capacitor.config.json` (`appName`).
- The APK bundles `www/index.html`. Online features (accounts, rooms) talk to your Firebase project, so they need internet.
- `debug.keystore` is a fixed test signing key, so every new build installs over the previous one without uninstalling (uninstall the old app once, the first time you switch to this key). Use it for testing only; a Play Store release needs its own private key.
- Each build gets a higher version number automatically (the workflow run number).
