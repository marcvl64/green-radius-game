# Green Radius Game

A self-ranking sustainability game for Burning Man theme camps. Spin a wheel
across six sectors — Water, Waste, Power, Transport, Food, Shelter — answer
Yes/No questions in four progressively harder tiers, and earn a unique green
radius for your camp.

This implementation is built from a Claude Design handoff bundle. The mechanics
and copy come from the Green Theme Camp Community's BLAST framework.

## Stack

- Static HTML + React 18 (loaded via UMD CDN)
- In-browser JSX via `@babel/standalone`
- No build step — `index.html` is the entry point

The whole site is three files:

| File              | Role                                                 |
|-------------------|------------------------------------------------------|
| `index.html`      | Page shell, fonts, mounts `<GreenRadiusGame/>`       |
| `green-radius.jsx`| Game component (wheel, modal, share card, state)    |
| `game-data.js`    | Sector / tier / question content from the BLAST PDF  |

## Run locally

Any static server works — for example:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Opening `index.html` directly via `file://` will not work because the JSX files
are loaded via `<script src>` and browsers block cross-origin reads from
`file://`.

## Deploy

The repo is configured for [Vercel](https://vercel.com). No build step or
framework — Vercel serves the files in this directory as-is.

```bash
vercel deploy --prod
```

## License

MIT — see `LICENSE`.
