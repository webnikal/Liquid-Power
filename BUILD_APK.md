# Liquid Power - APK banane ke 2 tareeke

## Tareeka 1: GitHub se (PC me kuch install nahi karna)
1. github.com par free account banao -> New repository (naam: liquid-power).
2. Is folder ki saari files (www, assets, package.json, capacitor.config.json, .github, .gitignore) us repo me upload karo.
   (.github folder upload karte waqt hidden folder dikhna chahiye; "Add file > Upload files" me drag-drop karo.)
3. Repo me Actions tab > "Build APK" > Run workflow dabao. 4-6 minute lagte hain.
4. Run complete hone par neeche "Artifacts" me `liquid-power-apk` download karo, zip kholo -> `app-debug.apk`.
5. APK ko phone me bhejo aur install karo (Settings me "Install unknown apps" allow karna padega).

## Tareeka 2: Apne PC par (Node 20 + JDK 17 + Android Studio/SDK chahiye)
npm install
npx cap add android
npx capacitor-assets generate --android --iconBackgroundColor "#03060d" --iconBackgroundColorDark "#03060d"
npx cap sync android
cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk
(portrait lock ke liye AndroidManifest.xml me <activity ... android:screenOrientation="portrait"> add karo.)

## Notes
- Ye debug APK hai: install aur test ke liye theek hai. Play Store ke liye signed release (AAB) banana padega.
- Game ka code www/index.html me hai. Isme badlav karo, phir dobara build karo.
- Fonts (Orbitron/Rajdhani) Google Fonts se aate hain: offline hone par game normal system font me chalega.
