# DiscordExt

Android app that loads the real Discord web client (discord.com/app) in a WebView,
with a built-in extension manager (🧩 button, bottom-right).

## Build
1. Open this folder in Android Studio (Koala or newer), let Gradle sync.
2. Build > Build APK(s). Output: app/build/outputs/apk/debug/app-debug.apk

## Extension API (available as `Ext` inside every extension)
- Ext.addCSS(css) -> returns an undo function
- Ext.storage.get(key, default) / Ext.storage.set(key, value)
- Ext.onReady(fn)
- Ext.observe(cssSelector, callback)  // calls back for each new matching element
- Ext.log(...)

Header format: see the samples in app/src/main/assets/samples/.

## Security
Extensions execute inside the Discord page, so they can read your session.
Only install extensions you wrote or fully reviewed.
Discord's ToS discourages modified clients; use at your own risk.

## Build without Android Studio
Push this folder to a GitHub repository. The workflow in .github/workflows/build.yml
builds the APK automatically: open the Actions tab, open the latest run, and download
the "DiscordExt-apk" artifact.
