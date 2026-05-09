# irc.rjplaton.com

A personal site styled as a late-90s mIRC channel running on a fake Win98 desktop. Pure HTML/CSS/JS, zero dependencies, single `index.html`.

Live at: https://irc.rjplaton.com

## What's in here

```
.
├── index.html              # the entire site (HTML + CSS + JS, single file)
├── assets/
│   └── audio/
│       └── song-of-storms-lofi.mp3
├── CNAME                   # GitHub Pages custom-domain marker
├── .gitignore
└── README.md
```

## Local preview

The Web Audio routing prefers HTTPS or `http://localhost` over `file://`, so the cleanest local preview is a tiny static server:

```bash
cd /path/to/this/repo
python3 -m http.server 8000
# then open http://localhost:8000
```

## Notes

- All edits are intentionally in a single `index.html`. Comments inside the file mark `[TODO]` placeholders for bio / projects / contact info — search the file for `[TODO`.
- Personal GitHub account only (per project conventions in `PROJECT_NOTES.md`, kept out of the repo).
