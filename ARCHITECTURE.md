# Architecture

## 1. System Overview

Browser or installed phone app → static site (`index.html`, manifest, service worker) → the six Yayasan systems, which open in their own tabs. The only network requests the portal makes itself are the status checks.

## 2. Tech Stack

| Area         | Tool                                                              |
|--------------|-------------------------------------------------------------------|
| Language     | HTML, CSS, vanilla JavaScript                                     |
| Framework    | None                                                              |
| Data         | None stored on a server. Browser `localStorage` keeps language, theme, 12/24h and Hijri day adjustment |
| Auth         | None in the portal. Each system handles its own login             |
| Time and dates | Built-in `Intl` with `Asia/Brunei` and the `islamic-umalqura` calendar |
| Offline      | Service worker (`sw.js`) caches the page and icons                |
| Testing      | Manual checks at phone and desktop sizes; headless browser screenshots |
| Distribution | Any https static host. Upload the six files into one folder       |

## 3. Project Structure

```
portal/
├ index.html             # Page, styles, scripts and the crest logo (inlined)
├ manifest.webmanifest   # Name, icons, colours, standalone display
├ sw.js                  # Service worker and cache version
├ icon-192.png           # App icon
├ icon-512.png           # App icon
├ icon-maskable.png      # Android adaptive icon
├ AGENTS.md              # Rules for AI coding agents
├ CLAUDE.md              # Imports AGENTS.md
└ docs/
  ├ PRD.md
  ├ DESIGN_SYSTEM.md
  └ ARCHITECTURE.md
```

## 4. Data Flow

1. The page loads and draws the header and one tile for each entry in `SYSTEMS`.
2. A clock loop reads the time in `Asia/Brunei` and updates the display every second.
3. The Hijri date is calculated from the Brunei date plus the saved day adjustment.
4. The page requests each system's address (a `no-cors` fetch, 7 second timeout) to set its status dot. It repeats every 90 seconds and when the page becomes visible or the device goes back online.
5. Tapping a tile opens that system in a new tab.

## 5. Scalability

- To add a system, add one entry to `SYSTEMS` in `index.html` with its icon, tint, link, and Malay and English text, then raise the `CACHE` version in `sw.js`.
- Keep features modular inside the single file. Don't add a build tool or library without updating this file.
- The status check can only tell whether the address responds, not whether the system's login or data is working.
