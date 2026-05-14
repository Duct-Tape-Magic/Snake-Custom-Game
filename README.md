[README.md](https://github.com/user-attachments/files/27779721/README.md)[Uploading README.md…]# Slither — Fluid Snake

A single-player, slither.io-style snake game. Smooth 360° movement, mouse-controlled, with glowing orbs, a 7-lives system, crash and respawn screens, and a persistent high score saved in your browser.

Built as one self-contained `index.html` — no build step, no dependencies. Drop it on any static host and it works.

## How to play

- **Aim** with your mouse — the snake's head smoothly turns toward the cursor.
- **Boost** by holding the left mouse button or `Space` (costs a bit of length while held).
- **Pause** with `P`.
- **Eat** the glowing orbs to grow and score.
- **Don't hit the walls.** You start with 7 lives. Hitting a wall pauses the game and shows a crash screen. If you have lives left, the **Respawn** button drops you back into the arena at a safe spot. When lives reach zero, it's **Game Over**.
- Your best score is saved in your browser between sessions.

## Run it locally

You can just double-click `index.html` and it'll open in your browser. If you'd rather serve it (some browsers are stricter about local files):

```bash
# Python 3
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy it to GitHub Pages

This is the simplest free way to put it on the public web.

### 1. Create a new GitHub repository

- Go to <https://github.com/new>
- Name it something like `snake-game` (or anything you want)
- Make it **Public** (required for free GitHub Pages)
- Do **not** initialize with a README — we already have one
- Click **Create repository**

### 2. Push this folder to the repo

Open a terminal in this folder (the one containing `index.html` and `README.md`) and run:

```bash
git init
git add .
git commit -m "Initial commit: slither snake game"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

Replace `YOUR-USERNAME` and `YOUR-REPO` with your actual values. The URL is shown on the repo's empty-state page right after you create it.

### 3. Enable GitHub Pages

- In your repo on GitHub, click **Settings** (top right of the repo)
- In the left sidebar, click **Pages**
- Under **Build and deployment**, set:
  - **Source:** Deploy from a branch
  - **Branch:** `main`, folder `/ (root)`
- Click **Save**

GitHub will show a banner saying the site is being built. After about a minute, refresh the page — it'll display a green box with your live URL, something like:

```
https://YOUR-USERNAME.github.io/YOUR-REPO/
```

That's your game, live on the web.

### 4. Push updates later

Any change you make locally goes live with the usual git workflow:

```bash
git add .
git commit -m "Describe your change"
git push
```

The site rebuilds automatically in under a minute.

## File layout

```
snake-game/
├── index.html   # the whole game — HTML, CSS, JS in one file
└── README.md    # this file
```

## Tweaking the game

All gameplay constants live at the top of the `<script>` block in `index.html`, under the `CONFIG` section. Some you might want to play with:

| Constant | What it does |
|---|---|
| `WORLD_W`, `WORLD_H` | Size of the playing arena |
| `STARTING_LIVES` | How many lives you start with |
| `STARTING_LENGTH` | Starting snake length (in path points) |
| `BASE_SPEED` / `BOOST_SPEED` | How fast the snake moves |
| `TURN_RATE` | How tightly the snake can turn (radians/frame) |
| `ORB_TARGET` | How many food orbs are on the board at once |
| `PATH_GROWTH_PER_ORB` | How much longer you get per orb |
| `SCORE_PER_ORB` | Points per orb |

Change a number, save, refresh — that's the dev loop.
()
