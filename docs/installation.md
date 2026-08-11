# Installation

This guide covers the public Windows release of Steve's Music Requests.

## Requirements

- 64-bit Windows.
- OBS Studio, if you want browser-source overlays.
- Stock Mixxx installed separately, if you want Mixxx request and Now Playing workflows.
- A Twitch channel and Twitch authorization for chat, Channel Points, or EventSub features.
- A local music-library folder for song requests.

## Install With The Installer

1. Download `Steves-Music-Requests-<version>-x64-win.exe` from GitHub Releases.
2. Run the installer.
3. Choose the install location.
4. Keep Desktop and Start Menu shortcuts enabled unless you do not want them.
5. Launch Steve's Music Requests from the installer, Desktop shortcut, or Start Menu.

## Zip Fallback

If Windows or antivirus blocks the installer:

1. Download `Steves-Music-Requests-<version>-x64-win.zip`.
2. Extract it to a normal user-writable folder.
3. Run `StevesMusicRequests.exe`.

The installer is preferred for normal use.

## First Launch Setup

1. Open Steve's Music Requests.
2. Connect your Twitch channel and complete Twitch authorization.
3. Choose and scan your music library.
4. Leave Mixxx mode on stock Mixxx unless you are specifically testing another bridge mode.
5. In OBS, add Browser Sources for the URLs shown by Steve.
6. For Now Playing, use the compact source size shown by Steve. The default is `640 x 150`; do not fit it to the full OBS canvas.
7. Add user-provided character assets only if you use Character Output.

Requests remain disabled until required Twitch setup is complete.

## Runtime Data

Installed builds keep user runtime data outside the installed application directory. This includes setup, Twitch authorization, config, logs, reports, browser session data, and user-selected assets.

The app can move the runtime folder from Settings > Advanced / Diagnostics > Choose Runtime Folder. The selected folder should be outside the installed app folder so updates and uninstall do not remove user data.

## Update

1. Close Steve's Music Requests.
2. Install the new official release over the previous app version.
3. Launch Steve and confirm Twitch, Mixxx, OBS outputs, and Now Playing still work.

Updates should preserve runtime data.

## Uninstall

Use Windows Apps & Features or the Start Menu uninstaller.

Uninstall removes installed app files. Runtime data is preserved so you can submit diagnostics or reinstall without losing setup state.