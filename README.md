# Pacer

Triathlon pacing calculator as a Progressive Web App. Calculates total race time from swim, bike, and run inputs with transition times.

## Features

- **4 distances**: Sprint, Olympic, Half Ironman, Ironman
- **Flexible input**: Switch between pace (min/100m, km/h, min/km) and duration per discipline
- **Transition times**: T1 (Swim > Bike) and T2 (Bike > Run) with defaults
- **Persistent state**: All inputs are saved to localStorage and restored on next visit
- **Installable**: Add to iPhone/Android home screen for app-like experience
- **Offline capable**: Works without internet after first load

## Tech Stack

- Single-file HTML/CSS/JS — no build tools, no dependencies, no frameworks
- Service Worker for offline caching
- Web App Manifest for home screen installation
- Google Fonts (Inter, JetBrains Mono)

## Local Development

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000` in your browser.

> **Note**: Service Workers require HTTP (not `file://`), so a local server is necessary.

## Deploy to GitHub Pages

```bash
git init
git add index.html manifest.json sw.js icon-192.png icon-512.png README.md
git commit -m "Initial commit"
gh repo create pacer --public --source=. --push
gh api repos/{owner}/pacer/pages -X POST -f "source[branch]=main" -f "source[path]=/"
```

The app will be available at `https://<username>.github.io/pacer/`.

## Install on iPhone

1. Open the URL in Safari
2. Tap "Share" > "Add to Home Screen"
3. The app runs fullscreen and works offline

## Project Structure

```
index.html      Main app (HTML + CSS + JS)
manifest.json   PWA manifest
sw.js           Service worker for offline support
icon-192.png    App icon 192x192
icon-512.png    App icon 512x512
```
