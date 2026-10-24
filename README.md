# Convince Me – User Journey Motion

A minimal animated flowchart of the Convince Me user journey. A small mascot runs through every step, from Launch app to the final Skip or Buy decision, lighting up each box and path as it goes.

**Live demo:** https://claude.ai/artifact/1Yz5BdiRaVEPdA9NiyVaoV

## Files

```
convince-me-journey/
├── index.html          the whole animation (HTML, CSS, JS in one file)
├── assets/
│   └── favicon.svg     mascot used as the browser tab icon
└── README.md
```

No build step and no dependencies. The only external request is Google Fonts (Fredoka and Nunito); the page falls back to system fonts if offline.

## Run it

Double-click `index.html`, or serve the folder:

```
python3 -m http.server 8000
```

then open http://localhost:8000.

## Controls

- **Pause / Play** freezes and resumes the motion.
- **Replay** restarts from Launch app.
- The Skip path and the Buy path alternate on each loop.

## Journey order

Launch app → Get started → Enter profile → Add monthly income → Choose priorities → Connect shopping apps → Personal dashboard → Browse shop → Open product → Add to cart → Review checkout → Tap pay → Impulse intervention → Answer 5 prompts → View recommendations → User Decision → Complete purchase (Buy) or Leave purchase (Skip) → back to the dashboard.

## Change the speed

In the `play()` function near the bottom of `index.html`:

| What | Where | Current value |
|---|---|---|
| Time to run along an arrow | `Math.max(800,L/.2)` | smaller numbers = faster |
| Rest on each box | `e[3]?0:900` | milliseconds |
| Hold on first box | `tw(1200,0,tk)` | milliseconds |
| Hold before loop restarts | `tw(3500,0,tk)` | milliseconds |

## Change the colours

Edit the variables at the top of the `<style>` block: `--hi` (mustard), `--acc` (coral), `--ink`, `--dim`, `--bg`. A dark theme switches on automatically from the system setting.

## Get your own URL

- **Netlify Drop:** go to app.netlify.com/drop and drag in this folder.
- **GitHub Pages:** push the folder to a repo, then Settings → Pages → deploy from the main branch.
- **Vercel:** run `vercel` inside the folder.

## Credits

Convince Me, Group 9, Business Ethics & Communication, guided by Diti Vyas.
