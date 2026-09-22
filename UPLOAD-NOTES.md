# Locker room — what to upload

Everything here goes into the **root of the YSB-experiments repo**, alongside
`index.html`, `menu-layout.html`, `baba-page.html` and the rest.

```
locker-room-3d.html              ← the page
locker-room-3d-assets/           ← its folder (keep the name, paths are relative)
    locker3d.js
    models/     locker.glb, boots.glb, bottle.glb, goggles.glb,
                soccer-ball.glb, cricket-ball.glb, cricket-bat.glb
    textures/   wall.webp, floor.webp
    fonts/      7 × .woff2
```

That's it — 19 files, 1.3 MB. Nothing else changes, and nothing existing is
overwritten. `UPLOAD-NOTES.md` (this file) doesn't need to go up.

## Linking it from the menu

The new page does **not** replace `locker-room.html` — that's the older
dark-blue experiment, and it's left exactly as it is.

`menu-layout.html` currently has a card pointing at the old one:

```html
<a class="scrap rest oat" href="locker-room.html" data-seed="4678" aria-label="The Locker Room">
```

Either add a second card pointing at `locker-room-3d.html`, or change that
`href` if you'd rather the new build take over the slot. There's already a
`thumbs/locker-room.jpg` if you want to reuse it, or drop in a fresh
`thumbs/locker-room-3d.jpg`.

## The testimony pages

The two "open the locker" destinations now point at the pages already in the
repo — `baba-page.html` and `sean-frisbee.html`. No copies are shipped here, so
there's one version of each to maintain.

They have no "back to the locker room" link, so the browser back button is the
way out. Say the word and I'll add one.

## Serving

Needs to be served over http/https (any static host, GitHub Pages included) —
opening the file straight off disk won't load the models. That was true of the
old prototype too.
