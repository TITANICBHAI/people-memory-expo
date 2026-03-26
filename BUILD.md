# People Memory — Build & Privacy Reference

---

## Privacy Policy (Expo App)

The privacy policy is a **native screen built into the app** — no external link needed.

**Location in codebase:** `app/privacy.tsx`

**What it covers:**
| Section | Summary |
|---|---|
| Data Collection | Nothing collected — all data stays on device |
| Data Storage | AsyncStorage (local, never synced) |
| Notifications | Local only, no external server |
| Photos & Camera | Stored locally, never uploaded |
| Third-Party Services | None — no analytics, ads, or tracking |
| Data Deletion | Delete per-contact or uninstall to wipe all |
| Children's Privacy | Not directed at under-13s |

**Hosted version (GitHub Pages):**
`https://titanicbhai.github.io/people-memory/privacy-policy.html`

---

## Blazor WebAssembly — Build Commands

> Blazor is a **web app** (runs in the browser). It does not produce an APK.
> Output is a static site you can host on any web server or CDN.

### Prerequisites
- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)

### Run locally (development)
```bash
dotnet run
```
Starts a local dev server at `https://localhost:5001`

### Build for production
```bash
dotnet publish -c Release
```
Output → `publish/wwwroot/`
That folder is your deployable static web app.

### Deploy to GitHub Pages (one-time setup)
```bash
# From the publish/wwwroot folder
dotnet publish -c Release -o ./output
# Then push ./output/wwwroot to a gh-pages branch
```

### Deploy to any static host (Netlify, Vercel, etc.)
Just drag & drop the `publish/wwwroot/` folder — no server required.

---

## Expo (React Native) — Build Commands

> This is the mobile app that produces **APK** (Android) and **IPA** (iOS).

### Prerequisites
```bash
npm install -g eas-cli
eas login           # sign in to your Expo account
```

### Development build (simulator / USB)
```bash
# Android APK (USB install)
eas build --platform android --profile development

# iOS Simulator
eas build --platform ios --profile development
```

### Preview build — APK direct install (no Play Store)
```bash
eas build --platform android --profile preview
```
Produces a `.apk` file you can send directly and install.

### Production build — App Store / Play Store
```bash
# Android AAB (Play Store)
eas build --platform android --profile production

# iOS IPA (App Store)
eas build --platform ios --profile production

# Both at once
eas build --platform all --profile production
```

### Submit to stores
```bash
# After a production build completes:
eas submit --platform android
eas submit --platform ios
```
> Fill in your Apple ID, ASC App ID, and Team ID in `eas.json` before submitting.

### App IDs
| Platform | ID |
|---|---|
| iOS Bundle ID | `com.peoplememory.app` |
| Android Package | `com.peoplememory.app` |
| Expo Project ID | `ed99f22b-69c6-4f88-a9cc-cb0ce7e14a70` |

---

## Repos

| App | Repo |
|---|---|
| Expo (React Native) | https://github.com/TITANICBHAI/people-memory-expo |
| Blazor (Web) | https://github.com/TITANICBHAI/people-memory-blazor |
| Combined (archive) | https://github.com/TITANICBHAI/people-memory |
