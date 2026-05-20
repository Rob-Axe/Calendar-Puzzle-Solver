# The Whole Year Puzzle — Solver

An interactive solver for **The Whole Year Puzzle** by Palmetto Puzzle Works — a wooden
calendar brain-teaser. Pick a date and the nine pieces rearrange to leave exactly that
month and day uncovered.

👉 **[Open the solver](index.html)** (or enable GitHub Pages — see below)

![The puzzle: a wooden calendar tray with nine polyomino pieces](#)

## How it works

The tray is a 7×7 grid with **43 playable cells**:

- Two rows of months (Jan–Jun, Jul–Dec), with the top-right corner notched out
- Four full rows of days (1–28)
- A final row holding 29, 30, 31

The **9 pieces** cover **41 cells**, leaving 2 free — the chosen month and day.

| Piece | Shape | Cells |
|-------|-------|------:|
| L4 | L: 3 down, 1 right | 4 |
| P  | 2×2 square + 1 below | 5 |
| O  | 2×2 square | 4 |
| U  | C / U-pentomino | 5 |
| L5 | L: 4 up, 1 right | 5 |
| N  | Z/N-pentomino | 5 |
| X  | cross | 5 |
| T  | T-tetromino | 4 |
| Z  | S/Z-tetromino | 4 |

Total: **41 cells**, plus 2 free = 43 ✓

Solving is an **exact-cover** problem. The solver tries every rotation and reflection of
each piece, using most-constrained-cell branching to stay fast. Every one of the 366
possible dates has at least one solution.

## Features

- Pick any month + day
- **One solution** (instant) or **all solutions** with a thumbnail gallery and prev/next navigation
- Each piece rendered in its own color; the free month/day cells highlighted
- Runs entirely in the browser — no build step, no dependencies

## Usage

Just open `index.html` in any modern browser — desktop or mobile. No install,
no build step, no dependencies.

## Putting it online (free) with GitHub Pages

Hosting the solver on GitHub Pages gives you a public link you can open on any
phone or share with anyone.

### Step by step

1. **Push this repo to GitHub.** Create a new repository (for example
   `whole-year-puzzle`) and push these files to it. From the unzipped folder:

   ```bash
   git init
   git add .
   git commit -m "The Whole Year Puzzle solver"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```

2. **Open the repository on github.com** and click the **Settings** tab
   (top right of the repo page).

3. In the left sidebar, click **Pages** (under the "Code and automation" group).

4. Under **Build and deployment → Source**, choose **Deploy from a branch**.

5. Two dropdowns appear. Set the first to **`main`** and the second to
   **`/ (root)`**, then click **Save**.

6. Wait about 30–60 seconds and refresh the page. A green banner appears at the
   top with your live link:

   ```
   https://<your-username>.github.io/<repo-name>/
   ```

   That's your shareable URL. It works because the app file is named
   `index.html`, which GitHub Pages serves automatically.

### Using it on your phone

1. Open the GitHub Pages link above in your phone's browser
   (Safari on iPhone, Chrome on Android).
2. Optionally, add it to your home screen so it opens like an app:
   - **iPhone (Safari):** tap the **Share** button → **Add to Home Screen**.
   - **Android (Chrome):** tap the **⋮** menu → **Add to Home screen**.
3. Tap the icon any time to launch the solver. After the first load it works
   even with a weak connection — the whole app is one small file.

> **Note:** the app loads its display font from Google Fonts. With no internet
> it still works perfectly, just with a standard system font instead.

### Other free hosting options

If you don't want to use GitHub Pages, you can drag `index.html` onto
[Netlify Drop](https://app.netlify.com/drop) or deploy it with
[Cloudflare Pages](https://pages.cloudflare.com/). Both give you an instant
public link with no command line needed.

## Project structure

```
.
├── index.html    # the entire app — geometry, solver, and UI in one file
├── README.md
└── LICENSE
```

## Credits

- Puzzle: **The Whole Year Puzzle** by [Palmetto Puzzle Works](https://www.palmettopuzzleworks.net/)
- This solver is an independent fan project and is not affiliated with Palmetto Puzzle Works.

## License

MIT — see [LICENSE](LICENSE).
