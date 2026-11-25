# Product Requirements Document

## 1. Product Overview

- **Product Name:** SYSHHB IT Portal
- **Tagline:** One place to open every Yayasan SHHB system.
- **Description:** A web portal and installable phone app for Yayasan Sultan Haji Hassanal Bolkiah. It shows one button for each school system, a live clock in Brunei time, and the Gregorian and Hijri dates. It works on phone and desktop, in Malay and English.

## 2. Problem

Each Yayasan system (helpdesk, purchases, inventory, documents, recorder, school map) lives at its own web address. People have to remember or bookmark every one, and cannot tell at a glance whether a system is reachable.

## 3. Goal

Let anyone open any Yayasan system in one tap or click from a single page, on a phone or a desktop.

## 4. Target Users

- Yayasan SHHB staff and teachers who use the school IT systems
- IT staff who run and support the systems
- People using the portal on a phone, installed as an app

## 5. Core Features (Version 1)

- **System buttons:** one tile for each system, opening in a new tab: SYSHHB IT Helpdesk, IT Purchase Tracker, IT Asset Inventory, Document Library, IT Recorder and School Map.
- **Live status:** a green, red or amber dot on each tile, plus an "x/6 online" summary that can be refreshed by tapping it.
- **Brunei clock:** large time in `Asia/Brunei` (GMT+8) with a seconds ring around the crest, switchable between 12-hour and 24-hour.
- **Dates and calendar:** Gregorian and Hijri dates, with a monthly calendar that shows the Hijri day under each date and a day adjustment because local sighting can differ by a day.
- **Language and theme:** Malay and English switch, and light and dark mode.
- **Installable app:** installs on Android (Chrome, Edge) as an app with the green crest icon. iPhone uses "Add to Home Screen".
- **Quick open:** keys 1 to 6 open a system on desktop.

## 6. Out of Scope (for now)

- Login or single sign-on in the portal itself (each system handles its own login)
- Search box for systems (removed on request)
- Push notifications
- Offline use of the systems themselves

## 7. Success Metrics

Proposed, to be confirmed by the owner:

- The header and all system tiles fit on one phone screen without scrolling.
- The portal installs as an app, not a shortcut, on Android.
- Any system opens in one tap from the home screen icon.
- The Hijri date matches the official Brunei date, using the day adjustment when needed.
