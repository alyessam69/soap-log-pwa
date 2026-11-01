SOAP BAR DAILY LOG - PWA PACKAGE
================================
Files
  index.html                 the app (all code inside, no internet needed after the first load)
  manifest.webmanifest       app name, colours, icons (makes it installable)
  sw.js                      service worker (offline support + automatic updates)
  icons/                     icon-192.png, icon-512.png, icon-maskable-512.png

IMPORTANT: a PWA must be served over HTTPS (or from localhost). Opening index.html directly from the folder
still works as a normal page, but "Install" and offline caching only work when it is hosted.

Option A - free hosting (recommended, works on your phone)
  1. Netlify: open app.netlify.com/drop and drag this whole folder onto the page. You get an https link.
     (GitHub Pages or Cloudflare Pages also work: upload the folder contents, keep the file names as they are.)
  2. Open the link on the phone.
       Android (Chrome): menu (three dots) > Install app / Add to Home screen.
       iPhone (Safari): Share button > Add to Home Screen.
  3. Open it once with internet; after that it also opens offline.

Option B - on the PC only
  Open a terminal in this folder and run:  python -m http.server 8080
  Then open http://localhost:8080 in Chrome or Edge and use the install icon in the address bar.

Updating the app
  Replace index.html on the host with the new version and open the app once while online.
  The service worker is network-first, so the new version loads by itself. To force it, change
  CACHE = 'soaplog-v1' in sw.js to 'soaplog-v2'.

Your data
  Auto-save stores data inside the browser/app (localStorage). It is separate from any other copy of the page
  you used before. To move old data: in the old page use Export backup (Settings), then in the installed app
  use Import backup. Export a backup now and then. Clearing the browser/app data erases the saved entries.

Notes
  - Copy as image needs https (hosting) to reach the clipboard; Export to Excel works anywhere.
  - The Line 3 option (6 soaps / 5 soaps) is in the top bar.
