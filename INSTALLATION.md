# Installation Guide — Dhruv Khant GitHub Profile README

## Folder Structure

```
DhruvKhant/           ← Create a repo with your GitHub username
├── README.md
├── INSTALLATION.md
└── assets/
    ├── header.svg
    ├── divider.svg
    ├── neural-brain.svg
    ├── skills-galaxy.svg
    ├── timeline.svg
    ├── ai-lab.svg
    ├── ml-universe.svg
    ├── stats-dashboard.svg
    └── ending.svg
```

---

## Step 1 — Create the Special Profile Repository

1. Go to **github.com → New repository**
2. Name the repository **exactly** your GitHub username (e.g., `DhruvKhant`)
3. Make it **Public**
4. Check **"Add a README file"**
5. Click **Create repository**

This is GitHub's special profile repo — the `README.md` in this repo
appears on your public profile page.

---

## Step 2 — Upload Files

1. Delete the default `README.md`
2. Upload all files from this package:
   - `README.md`
   - All files in `assets/` folder

You can do this via:
- **GitHub web UI**: Drag-and-drop files
- **Git CLI**:
  ```bash
  git clone https://github.com/DhruvKhant/DhruvKhant
  cd DhruvKhant
  # Copy all files here, then:
  git add .
  git commit -m "feat: cinematic profile README"
  git push origin main
  ```

---

## Step 3 — Update Your Username in README.md

Replace all instances of `DhruvKhant` with your actual GitHub username
in `README.md`. They appear in:

- GitHub Stats widget URLs
- Streak Stats widget URL
- Trophies widget URL
- Activity graph URL
- Profile Views counter URL
- Social links section

---

## Step 4 — Optional: Snake Contribution Animation

Add the contribution snake animation via GitHub Actions:

1. Create `.github/workflows/snake.yml` in your profile repo:

```yaml
name: Generate Snake Animation

on:
  schedule:
    - cron: "0 12 * * *"   # Runs daily at noon UTC
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

2. In `README.md`, uncomment the **Option B** snake section under Section 8.

---

## Step 5 — WakaTime Integration (Optional)

If you use WakaTime for coding stats:

1. Sign up at **wakatime.com** and install the plugin in your editor
2. Get your WakaTime API key
3. Add it as a GitHub secret: `Settings → Secrets → WAKATIME_API_KEY`
4. Replace the Top Languages widget URL with:
   ```
   https://github-readme-stats.vercel.app/api/wakatime?username=YOUR_WAKATIME_USERNAME&theme=transparent&title_color=00d4ff&text_color=ffffff&border_color=7b2fff&layout=compact
   ```

---

## Stats Widgets Reference

| Widget | Service | Customizable |
|--------|---------|-------------|
| GitHub Stats | github-readme-stats | theme, colors, icons |
| Top Languages | github-readme-stats | layout, lang count |
| Streak Stats | streak-stats.demolab.com | ring, fire, label colors |
| Trophies | github-profile-trophy | theme, columns |
| Activity Graph | activity-graph.vercel.app | bg, line, area colors |
| Profile Views | komarev.com/ghpvc | color, style, label |

All widgets are free and automatically update. No API key needed for basic stats.

---

## Color Reference (for customization)

| Color | Hex | Used for |
|-------|-----|---------|
| Electric Blue | `#00d4ff` | Primary accent, borders |
| Cyber Purple | `#7b2fff` | Secondary accent, glow |
| Neon Cyan | `#00ffcc` | Tertiary, success states |
| Deep Dark | `#030308` | Background |
| Grid Blue | `#111130` | Card backgrounds |

---

## Performance Notes

- All SVG animations are **CSS-based** — no JavaScript, no external dependencies
- SVGs are rendered as `<img>` tags — GitHub sandboxes them safely
- Animations play natively in all modern browsers and GitHub's renderer
- Total profile load is primarily the stats widget API calls (cached by GitHub)
- All custom SVGs are self-contained and render offline

---

## Troubleshooting

**SVG not showing animation?**
→ GitHub renders SVGs in a sandboxed iframe. CSS `@keyframes` animations work.
→ JavaScript-based animations do NOT work — the files here use only CSS.

**Stats showing "not found"?**
→ Replace `DhruvKhant` with your exact GitHub username (case-sensitive).

**Streak not loading?**
→ streak-stats.herokuapp.com may be rate-limited. Try streak-stats.demolab.com.

**Activity graph missing?**
→ The graph needs some commit activity to render. New accounts show an empty grid.

---

*Built with custom SVG animations — no templates, no generators.*
