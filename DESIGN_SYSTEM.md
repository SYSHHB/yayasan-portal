# Design System

Sizes are px on the web.

## 1. Brand Identity

Clean, modern, official, calm. Green and yellow taken from the Yayasan crest.

## 2. Colour Palette

| Name        | Light     | Dark      | Use for                                   |
|-------------|-----------|-----------|-------------------------------------------|
| Primary     | `#27a047` | `#27a047` | Header top, buttons, app theme colour     |
| Primary dark| `#157a35` | `#157a35` | Header bottom, today highlight            |
| Pine        | `#0d3b26` | `#0d3b26` | Text on yellow badges                     |
| Sun         | `#f8f038` | `#f8f038` | Seconds, ring, highlights on green        |
| Background  | `#eef4ee` | `#09130d` | Page background below the header          |
| Card        | `#ffffff` | `#14231a` | Tiles, calendar sheet                     |
| Text        | `#10241a` | `#eaf4ec` | Main text                                 |
| Muted       | `#5f7466` | `#93aa9a` | Descriptions, labels                      |
| Online      | `#22c55e` | `#22c55e` | System reachable                          |
| Offline     | `#ef4444` | `#ef4444` | System not reachable                      |
| Checking    | `#f59e0b` | `#f59e0b` | Status check running                      |
| Friday      | `#d0453a` | `#d0453a` | Friday in the calendar                    |

Tile icon tints (light, strong):

| System          | Light     | Strong    |
|-----------------|-----------|-----------|
| Helpdesk        | `#d9f5e0` | `#7fd596` |
| Purchase Tracker| `#fff3c4` | `#f3cf4f` |
| Asset Inventory | `#d8ebff` | `#7bb6f0` |
| Document Library| `#ece2ff` | `#b497ef` |
| IT Recorder     | `#ffe0e0` | `#f09a9a` |
| School Map      | `#d6f3f1` | `#6fcfc6` |

The header is a vertical gradient from `#27a047` (top) through `#1b8a3c` to `#0f6b30` (bottom). Its top colour must equal the manifest `theme_color` and `background_color`.

## 3. Typography

- **Font:** Inter if available, then the system font (`system-ui`, `-apple-system`, `Segoe UI`, `Roboto`). No font files are loaded.
- **Page title:** 19 to 30, weight 800
- **Time:** 40 to 68, weight 800, tabular numbers
- **Seconds:** 20 to 32, weight 700, Sun colour
- **Tile title:** 13.5 to 18, weight 750
- **Body / description:** 11 to 14, regular
- **Label caps:** 11 to 12, weight 800, letter spacing 1.4

Sizes use `clamp()` with `vh`, so the header shrinks on short screens.

## 4. Spacing

Use 4, 8, 12, 16, 24. Gaps between tiles are 10 on phone and 18 on desktop.

## 5. Border Radius

- Header bottom corners: 34
- Tiles and the clock card: 26
- Date chips: 18
- Icon tiles: 14 to 20
- Buttons and pills: fully round (999) or 12 to 16
- Calendar sheet: 30 on top corners on phone

## 6. Components

- **Tile:** white card, icon on a tinted rounded square with a status dot, title, 2-line description, round "↗" button top right. On hover (desktop) a soft glow in its tint follows the cursor and the card lifts.
- **Clock card:** frosted glass (white at 13%, blur), crest with a Sun ring that fills once a minute, time, small 24H/12H button.
- **Date chip:** frosted glass, calendar or moon icon, label and date. Tapping opens the calendar.
- **Status pill:** white pill with a dot and "x/6 online", tapping refreshes.
- **Calendar:** bottom sheet on phone, centred dialog on desktop. Today is a green filled square, the Hijri day is shown small under each date.

## 7. Icons

Emoji for each system (🛠️ 🧾 💻 📁 🎙️ 🗺️), shown on a tinted rounded square. Controls use plain text symbols (↗ ‹ › ↻ ✕).

## 8. Breakpoints / Size Classes

- Phone: under 720. Two columns of tiles; a last tile alone spans the full width. Header and tiles fit one screen at 390x780.
- Tablet and desktop: 720 and over. Header content is centred in a 760 column; tiles sit in a centred 3 per row layout.
- Wide desktop: 1100 and over. Tile area is up to 1000 wide.

## Rules

- Never use colours outside this palette
- Design for the smallest supported screen first. Every screen must work there
- The crest logo never moves
- Every colour has a dark mode value
- Respect `prefers-reduced-motion`
