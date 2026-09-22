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
testimonies/                     ← the two pages a locker opens into
    baba.html
    sean.html
```

21 files, 3.3 MB. Nothing existing is overwritten.
`UPLOAD-NOTES.md` (this file) doesn't need to go up.

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

`testimonies/baba.html` and `testimonies/sean.html` are your Locker room folder
versions — the ones carrying the fixed "‹ Locker room" chip top-left — with two
changes:

- the chip now points at `../locker-room-3d.html`
- the remote `<script src="https://cdn.discordapp.com/…">` that was sitting at
  the top of `sean.html` is gone

Both are otherwise byte-identical to your copies. They're separate from the
repo's own `baba-page.html` and `sean-frisbee.html`, which `menu-layout.html`
links to and which stay as they are — so if you edit a testimony page, it needs
doing in both places.

## Serving

Needs to be served over http/https (any static host, GitHub Pages included) —
opening the file straight off disk won't load the models. That was true of the
old prototype too.
