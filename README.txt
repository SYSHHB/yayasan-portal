YAYASAN PORTAL — INSTALLABLE WEB APP (PWA)

This package is designed to let the portal be installed as a home-screen/desktop web app on supported phones and computers.

FILES TO PUBLISH TO THE SAME GITHUB PAGES PUBLISHING ROOT:
- index.html
- manifest.webmanifest
- service-worker.js
- icons/icon-192.png
- icons/icon-512.png

IMPORTANT: Upload the extracted files/folders, not only the ZIP. Do not place them inside an extra nested folder. The manifest, service worker, and icons must sit beside the published index.html at the root of the site (for the custom domain https://portal.syayasan.edu.bn).

GITHUB PAGES STEPS:
1. Open the repository that publishes portal.syayasan.edu.bn.
2. Go to Settings > Pages and confirm the source/publishing location (branch root, /docs, or GitHub Actions).
3. Upload the files above into that exact publishing location, preserving the icons/ folder and exact lowercase filenames.
4. Commit/push and wait for the Pages deployment to finish.
5. Check these URLs and make sure each loads, not 404:
   https://portal.syayasan.edu.bn/manifest.webmanifest
   https://portal.syayasan.edu.bn/service-worker.js
   https://portal.syayasan.edu.bn/icons/icon-192.png
   https://portal.syayasan.edu.bn/icons/icon-512.png
6. In Settings > Pages, confirm the custom domain is correct and Enforce HTTPS is enabled when available. If the browser says "Not secure", resolve the domain/DNS/certificate issue first; code cannot fix the certificate by itself.

INSTALL:
- Android: Open the live HTTPS site in Chrome, reload, tap the portal's Install App button or Chrome menu (⋮) > Install app / Add to Home screen.
- Windows laptop/desktop: Open in Chrome or Edge, then use the Install icon in the address bar or browser menu.
- macOS laptop: Use Chrome/Edge Install option where available. Safari users can add a website to the Dock on supported macOS versions.
- iPhone/iPad: Open the live HTTPS site in Safari > Share > Add to Home Screen. iOS does not use the same Chrome install prompt as Android.
- Other browsers/devices: Availability depends on the browser and operating system. This is a Progressive Web App, not separate native APK/EXE installers.

TROUBLESHOOTING:
- If any URL above returns 404, upload the missing file to the actual published root.
- If the browser says "Not secure", fix HTTPS/certificate/DNS before trying to install.
- After deployment, reload the site. If an older version persists, close the portal tabs and reopen it; service worker updates may take a moment.
