# ASHOK GPT — Android Upgrade Starter

This is an Android-wrappable app project built around a responsive black/gold UI.

## Included now
- Chat history saved locally on the device
- Provider settings for OpenRouter, OpenAI, Google Gemini, and custom OpenAI-compatible endpoints
- Actual text chat requests once you supply your own provider API key and model ID
- Coding Lab, Minecraft Studio, Creative Studio prompt workflows
- Text/source/log file reading and attachment context
- GitHub Actions workflow that builds a debug APK artifact

## Important limitations
- This is not a fully autonomous coding agent. It generates code and build instructions; it does not run Gradle or compile a Minecraft JAR from inside the app.
- Image/video generation is not implemented; Creative Studio creates prompts/briefs.
- No login/cloud sync is included. History and API key are stored in browser/app local storage.
- A key stored client-side is not fully secure. For a public production app, replace direct client API calls with a private backend that keeps provider keys secret and applies rate limits. Never commit API keys to GitHub.
- API calls may cost money. Check the provider's current prices and usage limits; lifetime-free use cannot be promised.

## Build the Android APK using GitHub Actions (phone-friendly)
1. Upload the ZIP contents into the root of your `ashok-gpt` GitHub repository. Keep the top-level files in the repository root. Add the workflow at the exact path `.github/workflows/build-apk.yml`; if the mobile upload screen hides the `.github` folder, create that workflow file manually in GitHub using **Add file → Create new file** and paste the workflow contents from the ZIP.
2. Commit to the `main` branch.
3. Open the repository's **Actions** tab.
4. Choose **Build ASHOK GPT Android APK** → **Run workflow** (or wait for the push-triggered build).
5. Open the completed workflow run, scroll to **Artifacts**, and download `ASHOK-GPT-debug-APK`.
6. Extract the ZIP artifact and install `app-debug.apk` on your Android phone. Android may ask you to allow installs from that browser/file manager; only install APKs you built/trust.

The debug APK is for testing. A Play Store release needs a signed release build and app-store compliance work.

## GitHub Pages
The root `index.html`, `app.js`, `style.css`, and `manifest.json` are also the GitHub Pages website assets. Do not put API keys in source files.


## v3 workspace additions
- Local profile: display name, about text and preferred response language.
- App preferences: dark/dim appearance, concise/balanced/detailed response preference, Enter-to-send toggle.
- Chat history screen with local message search and JSON export.
- Existing AI Chat, Coding Lab, Minecraft Studio, Creative Studio, File Reader, provider settings, connection test, and local data controls retained.
- Android APK workflow: `.github/workflows/build-apk.yml` builds a debug APK on GitHub Actions and uploads it as `ASHOK-GPT-debug-APK`.

## Important limitations
This is a client-side prototype, not a full cloud account service. Profile/preferences/history are local to the device/browser. A provider API key saved in a client app can be extracted; for a public release, move provider calls to a secured backend. Coding and Minecraft Studio generate instructions/source text but do not themselves compile or test a JAR. Creative Studio currently creates prompts/briefs rather than generating image/video files. The APK must be built by running the GitHub Actions workflow; no compiled APK is included in this source ZIP.


## V4 logo branding update
- Added supplied ASHOK GPT logo image in `assets/ashok-gpt-logo.jpg`.
- Added 192px and 512px app/PWA icons.
- Added a short splash screen and logo in desktop/mobile headers.
- APK still needs to be built by the GitHub Actions workflow; this ZIP is source, not a compiled APK.
