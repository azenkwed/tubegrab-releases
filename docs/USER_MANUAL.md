# User Manual
Version: v0.3.10

## Overview
TubeGrab is a Qt desktop app for downloading audio or video using `yt-dlp` and `ffmpeg`. It stores your preferences in a local `settings.json` so your choices persist between launches.

## Quick Start
1. Paste a YouTube or YouTube Music URL.
2. Choose a download folder (default is your OS Downloads folder).
3. Select **Download Type** (Audio or Video).
4. Click **Download** and watch progress in the log panel.

## Download Types
- **Audio**: Extracts audio and converts it to the chosen format (mp3, m4a, opus).
- **Video**: Downloads the best available video+audio and merges into the chosen container (mp4, mkv).

## Playlists
- **Single item**: Forces a single video even if the URL belongs to a playlist.
- **Playlist (multiple)**: Downloads the full playlist when a playlist URL is provided.

## Dry Run
Enable **Dry run (no download)** to simulate a download without saving files. The app will still validate the URL and show output in the log.

## Log Panel
The log panel is hidden by default. Use the **Log Output** accordion header to expand or collapse the panel.

## Settings
The app auto-saves your preferences to `settings.json` in your OS app config folder. Saved items include:
- Download folder
- Filename template
- Download type and formats
- Playlist mode
- Embed metadata/thumbnail toggles

Windows stores this file under `%LOCALAPPDATA%\tubegrab\TubeGrab\settings.json`.

## Filename Templates
The filename template controls how saved files are named. It uses `yt-dlp` field tokens.

Common tokens:
- `%(title)s`
- `%(artist)s` (when available)
- `%(ext)s`

Examples:
- `%(artist)s - %(title)s.%(ext)s`
- `%(title)s.%(ext)s`

## Buttons
- **Open Folder**: Opens the current download folder in your file manager.
- **About**: Shows the app version.
- **Donate**: Opens the support page in your browser.

## Tips & Troubleshooting
- If `yt-dlp` or `ffmpeg` is missing, the app will offer to download them when you start a download.
- On Linux, the automatic tool download targets x86_64 only; install compatible `yt-dlp`/`ffmpeg` manually on other architectures.
- If downloads fail, update `yt-dlp` and `ffmpeg` and retry.
- Canceling a download stops the process cleanly without showing an error popup.
- Use the **Default** button to reset the folder to your OS Downloads location.
- When **Embed metadata** is enabled, the description field is cleared.
