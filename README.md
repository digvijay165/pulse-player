# Pulse Player

**A bright, browser-based music discovery player.** Search a catalog of full-length tracks, play direct audio links, manage a listening queue, and save favorites on your device.

[Live player](https://pulse-player-0rdw.onrender.com/) · [GitHub repository](https://github.com/digvijay165/pulse-player)

## Features

- Search songs and artists through the open Audius API
- Play full-length tracks or paste a direct HTTPS audio URL
- Control playback, seeking, volume, repeat, shuffle, and speed from **0.5× to 4×**
- Play, reorder, remove, and clear tracks in the queue
- Save favorites and playback speed in this browser
- Browse by genre with a responsive layout for phones and desktops
- No account, API key, build step, or installation required

## Music sources

| Priority | Source | What Pulse supports |
| --- | --- | --- |
| 1 | Audius API | Search results, artwork, and full-length audio streams |
| 2 | Direct HTTPS audio URL | Audio files the browser can play; native HLS works only in browsers that support it |

Pulse needs a **direct audio URL**, not a YouTube or Spotify webpage. It does not resolve Spotify, YouTube, Telegram, or other platform links, The app plays full-length tracks from the Audius catalog, mostly independent artists, or audio sources you provide.

## Player controls

| Control | Action |
| --- | --- |
| Play link | Play a direct HTTPS audio URL |
| Add to queue | Add a direct audio URL without interrupting the current track |
| Queue title | Play that queued track next |
| Up / down arrows | Change a queued track's position |
| Speed menu | Set playback speed from 0.5× to 4× |
| Space | Play or pause when focus is outside a form or button |
| Ctrl+K / Cmd+K | Focus the search field |
| [ / ] | Decrease or increase playback speed |

## Run locally

1. Clone this repository.
2. Open `index.html` in a modern browser while connected to the internet.

For a local web server, run:

```sh
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Deploy on Render

Pulse is a static HTML, CSS, and JavaScript site. Use these settings for a Render Static Site:

- **Repository:** `https://github.com/digvijay165/pulse-player`
- **Branch:** `main`
- **Build command:** leave empty
- **Publish directory:** `.`

The live site is [pulse-player-0rdw.onrender.com](https://pulse-player-0rdw.onrender.com/).

## Configuration and privacy

Pulse has no server-side configuration or required environment variables. Favorites and playback speed are saved in local storage on the current browser and are not synced between devices. Search requests go directly from the browser to the Audius API; audio streams from Audius or the direct source you provide.

This is a single-user browser app. Telegram commands, login and access control, admin tools, server resource metrics, and bot-side stream resolvers are not part of Pulse.

## Inspiration

Pulse is an independent browser player with its own name, design, and implementation. It is not affiliated with or endorsed by other music or bot projects.
