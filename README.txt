YAYASAN PORTAL — INSTALLABLE WEB APP

Files:
- index.html: portal page
- manifest.webmanifest: app name, display mode and icons
- service-worker.js: offline cache and install support
- icons/: 192x192 and 512x512 app icons

DEPLOY:
1. Upload ALL files/folders in this package to the same folder on your website/GitHub Pages.
2. Publish the site over HTTPS (for example https://portal.syayasan.edu.bn).
3. Open the live HTTPS URL in Chrome or Edge and reload.
4. Choose Install App in the portal, or use the browser's Install option.
5. On iPhone/iPad, open in Safari > Share > Add to Home Screen.

IMPORTANT:
A single local HTML file cannot reliably be installed as a Progressive Web App. The manifest, service worker, and icons must be hosted alongside it on the same HTTPS origin. If the browser still reports "This app cannot be installed", check DevTools > Application > Manifest and Service Workers, and ensure the files are deployed at the paths shown in the HTML.
