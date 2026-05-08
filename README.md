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

## Deploy (GitHub Pages)

This repo is configured for GitHub Pages with a custom domain at `irc.rjplaton.com`.

1. Push to `main` on the personal `rjplaton` GitHub.
2. **Settings → Pages → Source:** "Deploy from a branch", branch `main` / root.
3. The `CNAME` file at the repo root tells Pages the canonical domain is `irc.rjplaton.com`.
4. Configure DNS at the domain registrar — see below.
5. After DNS resolves, GitHub auto-provisions a Let's Encrypt certificate (~5–60 min).

## DNS (subdomain `irc.rjplaton.com`)

Add **one CNAME record** at the DNS provider for `rjplaton.com`:

| Type  | Host / Name | Value                  | TTL  |
|-------|-------------|------------------------|------|
| CNAME | `irc`       | `rjplaton.github.io.`  | Auto |

(Replace `rjplaton` with the actual personal GitHub handle if different.)

To verify after a few minutes:

```bash
dig irc.rjplaton.com +short
# → rjplaton.github.io.
# → 185.199.108.153   (and three more 185.199.x.153 IPs)
```

## Notes

- All edits are intentionally in a single `index.html`. Comments inside the file mark `[TODO]` placeholders for bio / projects / contact info — search the file for `[TODO`.
- Personal GitHub account only (per project conventions in `PROJECT_NOTES.md`, kept out of the repo).
- The `assets/audio/song-of-storms-lofi.mp3` is a Zelda fan remix; Nintendo holds the underlying composition copyright. Hosting publicly is the owner's call — if the player should fall back to the in-browser synth, set `MP3_URL = null` in `index.html`.
