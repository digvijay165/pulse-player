# Pulse Player

**A bright, browser-based music discovery player.** Search any song and play it in full through the YouTube player or the Audius catalog, play YouTube or direct audio links, manage a listening queue, and save favorites on your device.

[Live player](https://pulse-player-0rdw.onrender.com/) · [GitHub repository](https://github.com/digvijay165/pulse-player)

## Features

- Search any song on YouTube for free (no key needed) and through the open Audius API
- Play full-length tracks or paste a direct HTTPS audio URL
- Control playback, seeking, volume, repeat, shuffle, and speed from **0.5× to 4×**
- Play, reorder, remove, and clear tracks in the queue
- Save favorites and playback speed in this browser
- Browse by genre with a responsive layout for phones and desktops
- No account, API key, build step, or installation required

## Music sources

| Priority | Source | What Pulse supports |
| --- | --- | --- |
| 1 | YouTube (IFrame Player + Data API) | Search any song, including mainstream hits, and play it in full in the embedded YouTube player |
| 2 | Audius API | Search results, artwork, and full-length audio streams from independent artists |
| 3 | YouTube link or direct HTTPS audio URL | Audio files the browser can play; native HLS works only in browsers that support it |

The link box accepts **YouTube links** and **direct audio URLs**. Spotify, Telegram, and other platform links are not supported. YouTube songs play in the visible YouTube player, which may show YouTube's own ads.

## Player controls

| Control | Action |
| --- | --- |
| Play link | Play a YouTube link or a direct HTTPS audio URL |
| Add to queue | Add a YouTube link or direct audio URL without interrupting the current track |
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

Pulse has no server-side configuration or required environment variables. YouTube search works without a key: it uses free public Piped and Invidious mirrors (tried in order), and songs still play in the official YouTube player. These mirrors are community-run and can go down. For more reliable search, set the optional `YT_API_KEY` near the top of the script in `index.html` to a YouTube Data API v3 key restricted to this site's address. Search results are cached in the browser for a day. Favorites and playback speed are saved in local storage on the current browser and are not synced between devices. Search requests go directly from the browser to YouTube and Audius; audio plays from the YouTube player, Audius, or the direct source you provide.

This is a single-user browser app. Telegram commands, login and access control, admin tools, server resource metrics, and bot-side stream resolvers are not part of Pulse.

## Inspiration

Pulse is an independent browser player with its own name, design, and implementation. It is not affiliated with or endorsed by other music or bot projects.
