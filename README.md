# Presence Studio

**English** · [한국어](README.ko.md)

**[Download for Windows](https://github.com/LUNA12379/presence-studio-releases/releases/latest)** · **[Browse source code](https://github.com/LUNA12379/presence-studio)**

Show what you're watching, listening to or working on with Discord Rich Presence, a desktop overlay and OBS.

**Windows 10/11 x64 · Edge / Chrome · YouTube · YouTube Music · SoundCloud · English / 한국어**

This repository hosts Windows installers, the update channel and user guides. The application and browser extension source are public in [presence-studio](https://github.com/LUNA12379/presence-studio).

## Downloads and source

| What you need | Where to find it |
| --- | --- |
| Install or update the Windows app | [Latest release](https://github.com/LUNA12379/presence-studio-releases/releases/latest) → **Assets** → `Presence-Studio-<version>-Setup.exe` |
| Read, change or build the app and extension | [Public source repository](https://github.com/LUNA12379/presence-studio) · [Build instructions](https://github.com/LUNA12379/presence-studio/blob/main/DEVELOPMENT.md) |
| Source matching a particular installer | [All releases](https://github.com/LUNA12379/presence-studio-releases/releases) → select the version → **Assets** → `Presence-Studio-<version>-source.zip` (2.8.0 and later) |

Releases from 2.8.0 onward include SHA-256 files and `release-manifest.json` linking the installer to its matching source. GitHub's automatic **Source code (zip / tar.gz)** downloads on the distribution repository contain its guides; choose the explicitly named `Presence-Studio-<version>-source.zip` for the application source.

## Source and license

Presence Studio 2.8.0 and later are **GPLv3 only with a narrow WebView2 linking/distribution permission**. See [COPYING](https://github.com/LUNA12379/presence-studio/blob/main/COPYING), [LICENSE](https://github.com/LUNA12379/presence-studio/blob/main/LICENSE) and [third-party notices](https://github.com/LUNA12379/presence-studio/blob/main/THIRD-PARTY-NOTICES.md). Read the [development guide](https://github.com/LUNA12379/presence-studio/blob/main/DEVELOPMENT.md) to build or contribute. Earlier installers are unchanged; their release pages do not contain the new matching-source bundle.

## Features

- Detect YouTube, YouTube Music and SoundCloud playback in Microsoft Edge or Google Chrome through the same browser extension.
- Customize activities with a title, status, image, link and elapsed or countdown timer.
- Save up to 30 presets, load them in the editor or apply them from the Presets page.
- Crop photos to 512 × 512 or 1024 × 1024 PNG, or keep the full image with transparent padding.
- Show an always-on-top desktop card or a transparent OBS Browser Source.
- Switch between English and Korean, with your choice saved across restarts.
- Check for updates from the public release channel in the app, then choose when to download and install.

## Install and connect

1. Download `Presence-Studio-<version>-Setup.exe` from [Releases](https://github.com/LUNA12379/presence-studio-releases/releases). The installer includes Node.js and downloads Microsoft WebView2 if missing. An internet connection may be needed. .NET Framework 4.7.2 or later is required.
2. Open Presence Studio and the **Discord desktop app**. Choose **EN / 한국어** in the top bar or first-run guide. New installations start in English; existing Korean installations keep Korean.
3. Choose **New Application** in the [Discord Developer Portal](https://discord.com/developers/applications). Use **the name you want displayed on Discord**. Copy the **Application ID** from General Information into **Connections & settings → Default Application ID**, then save. No password, user token or bot token is needed.
4. Copy the folder path from **Connections & settings → Connect browser extension**. Open `edge://extensions` in Edge or `chrome://extensions` in Chrome, enable **Developer mode**, choose **Load unpacked**, and select that folder. Refresh your YouTube and SoundCloud tabs. Install the extension in each browser you use. The **Edge extensions** button opens Edge's manager; Chrome users should enter `chrome://extensions` in Chrome's address bar.
5. Play a video or track. Enable **Share activity** in Presence Studio and activity sharing in Discord if it is disabled.

Microsoft Edge and Google Chrome are both supported. The extension is included with the installer and uses Chromium's Manifest V3; load the same folder in either browser. The **Browser extension** connection status applies to both browsers. Browser-store installation is not currently available. See the [Chrome instructions for loading an unpacked extension](https://developer.chrome.com/docs/extensions/get-started/tutorial/hello-world#load-unpacked).

The installer is not code-signed yet. Windows may show an unknown-publisher warning. Use files from the project's release page.

Edge and Chrome can run together, including multiple browser profiles. Since 2.8.0, their tab identities are separate. After updating, reload the extension bundled with the app and media tabs in every browser. If upgrading from a version older than 2.8.0, re-pin any previously pinned tab. The `storage` permission stores a random profile ID locally; it is not synced or sent to Discord.

## SoundCloud playback

After updating the app, open `edge://extensions` or `chrome://extensions` and reload **Presence Studio — YouTube & SoundCloud** (formerly **YouTube → Discord 활동**). Allow access to SoundCloud if your browser asks, then reload your SoundCloud tabs and start a track.

The extension reads the bottom miniplayer: track title, artist, cover art, playback position and pause state. You can browse another SoundCloud page while the track continues. SoundCloud uses **Listening** in automatic activity mode. A previously paused track restored when opening the site is ignored until you play it.

When several supported tabs are playing, the most recently started tab wins. Pause it to fall back to another playing tab, or use **Pin this tab** on the dashboard. Custom activities still take priority when selected. This version supports the SoundCloud website in the browser, not a separate desktop application. Private track links are not shared.

## Separate Discord application names

The current connection uses the registered application name. Under **Connections & settings → My Discord application**, save these IDs and click **Save ID and connect**:

| Field | Used for |
| --- | --- |
| **Default Application ID** | YouTube, YouTube Music, and any activity without a dedicated ID. |
| **SoundCloud Application ID** (optional) | SoundCloud playback. Create an application named SoundCloud if that is the name you want displayed. |
| **Custom activity Application ID** (optional) | Activities made in Customize, for example under the name Presence Studio. |

The connection switches automatically with the selected media tab or custom activity. Leave a dedicated field blank to use the default ID. One application is enough if you want the same name everywhere. IDs are saved on this PC and survive app and computer restarts; no bot token or server invitation is needed.

If the default application is named **YouTube**, SoundCloud and custom activities without dedicated IDs also appear under that name. This does not change what the extension detects. Discord controls the small logo in the activity header; naming an app SoundCloud does not guarantee an automatic SoundCloud logo.

## Images: two destinations

| Setting | Where it appears |
| --- | --- |
| **My images** | App preview, desktop overlay and OBS overlay. Files stay on this PC. |
| **Discord image** | The large image on the Discord activity card, selected from the connected application's Art Assets. |

To use the same photo in both places, choose it under **My images**, crop and save it, then use **Save as PNG**. Upload that PNG through **Register Discord image → Rich Presence → Art Assets**, save in the Developer Portal, and click **Refresh list** in the app. Images are not uploaded automatically. If you use a custom Application ID, upload to that application.

From **2.8.1**, the app compares its bundled extension version with the version actually running in each browser. A mismatch banner opens the version list in **Connections & settings → Browser extension**. Reload older extensions; update the app first if the extension is newer. Extension **1.3.0** reports its version even without media tabs. Older extensions appear as “Version unknown” when they send playback data; a disconnected extension cannot be inspected.

## Overlays, presets and updates

- **Desktop:** enable **Overlay → Show on desktop** and drag the card into position. Position lock and click-through are available.
- **OBS:** add a Browser Source and paste the address and dimensions from the app. Keep the address private: it includes a local access key. OBS works independently of the desktop-overlay switch.
- **Presets:** **Save as preset** uses the activity title as its name. Select it from **Saved presets** to load the editor, then click **Show this activity** to publish. Loading alone does not change your current activity.
- **Updates:** use **Connections & settings → App updates**. Enable **Check for updates when the app starts** to check on launch. Select **Download new version**, then **Install and restart** when ready. Checking does not download or install anything. Downloaded installers are checked against the release's SHA-256 digest before installation. If extension files change, reload the extension in your browser's extension manager and refresh YouTube and SoundCloud tabs.
- **Shortcuts:** `Ctrl+Shift+P` toggles sharing; `Ctrl+Shift+O` toggles the desktop overlay. Closing the window keeps the app in the tray. Use **Quit** to exit completely.

If you used an early build with an unconfigured update channel, install the latest Setup.exe once to connect it. Later releases can be installed from the app.

Application IDs, presets, images and language preferences live in `%APPDATA%\PresenceStudio`. They survive updates, restarts and uninstalling the app. Uninstalling keeps this folder so you can reinstall without losing your setup.

## Privacy and help

The extension sends current playback information to a local service on your PC. The app sends the selected activity to your Discord desktop client. It does not keep a watch-history database. Excluded keywords and pause hiding limit what is shared; Discord's privacy settings also apply. Configured external image URLs can be fetched by the app or Discord.

Reopen the guide from **Connections & settings → Open guide**. If the image list is empty, check that your ID matches the application where you uploaded the image, save the upload in the Developer Portal, then refresh the list.

Report ordinary problems through [source Issues](https://github.com/LUNA12379/presence-studio/issues), including the app version and steps to reproduce. Do not attach `config.json`, the generated `connection.js`, private overlay URLs or personal screenshots without reviewing them first.

For security issues, use [private vulnerability reporting](https://github.com/LUNA12379/presence-studio/security/advisories/new); do not publish credentials or exploit details in an issue.

Presence Studio is an independent project, not affiliated with Discord, Google, YouTube, SoundCloud or Microsoft.
