YAYASAN PORTAL — GITHUB PAGES INSTALL FIX (FLAT ROOT)

This package matches the flat file layout shown in your GitHub screenshot:
- index.html
- manifest.webmanifest
- service-worker.js
- icon-192.png
- icon-512.png
- CNAME (keep your existing CNAME file if it already contains portal.syayasan.edu.bn)

IMPORTANT: The previous manifest expected ./icons/icon-192.png and ./icons/icon-512.png, but your GitHub repository shows icon-192.png and icon-512.png at the repository root. That mismatch caused 404 errors. This package updates the manifest and service worker to use the root-level icon files.

UPLOAD:
1. Extract this ZIP.
2. In the GitHub repository publishing root, upload/replace index.html, manifest.webmanifest, service-worker.js, icon-192.png, and icon-512.png.
3. Keep the existing CNAME file with portal.syayasan.edu.bn.
4. Commit changes and wait for GitHub Pages deployment.

TEST THESE URLS AFTER DEPLOYMENT:
https://portal.syayasan.edu.bn/manifest.webmanifest
https://portal.syayasan.edu.bn/service-worker.js
https://portal.syayasan.edu.bn/icon-192.png
https://portal.syayasan.edu.bn/icon-512.png

Each should load successfully, not show 404.

CRITICAL HTTPS CHECK:
Your earlier screenshots showed "Not secure" even with an https:// URL. If Chrome/Edge still shows "Not secure", the domain's TLS certificate or DNS setup must be fixed in GitHub Settings > Pages and DNS before installation will work. In Settings > Pages, confirm the custom domain and enable Enforce HTTPS when GitHub makes it available. Allow DNS/certificate provisioning time. The ZIP cannot repair DNS or a TLS certificate.

ANDROID:
After all four test URLs work and the site is securely loaded, open the portal in Chrome, reload it, then use ⋮ > Install app or Add to Home screen. Edge uses its own menu and may label the option differently. If the install option is absent, open Chrome's site info and ensure the connection is secure, then clear site data/reload.
