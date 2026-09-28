# Medvault
For gathering my slides together
MedVault 🔐📚
MedVault is a private academic document vault for organizing PDFs, PowerPoints, Word documents, images, and other study materials.
It is intentionally not an AI study assistant, note-taking app, flashcard app, MCQ app, or PDF annotation tool.
What this repository contains
www/ — the MedVault web/PWA interface
capacitor.config.ts — Android app configuration
package.json — Capacitor dependencies
.github/workflows/build-apk.yml — automatic Android APK build
App ID: com.medvault.app
📱 Build the APK from your phone
You do not need Android Studio for the normal GitHub Actions build.
Create a GitHub repository named MedVault.
Upload the contents of this repository to it. Make sure .github/workflows/build-apk.yml is uploaded too.
Open the repository on GitHub and tap Actions.
Open Build MedVault APK.
Tap Run workflow if it has not already run from your upload.
Wait for the workflow to finish successfully.
Open the completed workflow run.
Scroll to Artifacts and download MedVault-debug-apk.
Extract the downloaded artifact and install app-debug.apk on your Android phone.
Every future push to main or master will also build a fresh APK automatically.
🔐 Supabase security
The app uses the Supabase publishable key in the browser/Android client. That is appropriate for a client app when Row Level Security and storage policies are configured correctly.
Never put a Supabase sb_secret_... or service_role key in this repository or inside the Android app.
Local build (optional)
On a computer with Android tooling installed:
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
The APK will be generated at:
android/app/build/outputs/apk/debug/app-debug.apk
.github
   └── workflows
       └── build-apk.yml
