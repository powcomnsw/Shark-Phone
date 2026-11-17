# Shark 6 phone page

A single static page (`index.html`) that shows the truck's last readings and trips from one file,
`shark-status.json`, which Shark Central leaves in the owner's own Dropbox app folder (Setup → Phone app on the
truck). It only reads; nothing here reaches or changes the truck.

- **Hosting:** any static host. On Vercel or Netlify import this repo and set the root directory to `webapp`
  (no build step). Then open the address on the phone and Share → Add to Home Screen.
- **Connecting:** paste the Dropbox app key (the same one given to the truck), open Dropbox, tap Allow, paste the
  code. Code flow with PKCE: no app secret; the key and refresh token stay in that browser's storage.
- **Try it without a truck:** add `?demo` (truck on) or `?demo=off` (truck off) to the address.
- **The file:** `v`, `updated` (ms), `state` on / off, `battery` / `fuel` `{pct, km}`, `rangeKm`, `odoKm`,
  `outsideC`, `tyresPsi` [LF, RF, LR, RR], `body` `{locked, doorsOpen, windowsOpen}`, `climate`, `driveMode`,
  `trip` (in progress), `trips` (newest first, 30), `week` `{cost, prev, electric, fuel}`, `charges` (15). Any
  reading the car didn't give is absent. Written by `remote/PhoneStatus.kt`; `shark-status.txt` beside it is
  the same as plain lines.
- Fonts: Archivo (SIL OFL). No BYD imagery in this folder.
