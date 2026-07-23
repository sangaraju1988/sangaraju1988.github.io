# Personal Site — Setup & Publish Guide

This is a plain HTML/CSS site, same approach as shadowmodder.github.io — no build step, no framework. GitHub Pages serves the files as-is.

## 1. Create the right repo

GitHub Pages gives you a free URL at `https://<username>.github.io` only if the repo is named **exactly** that:

1. On GitHub, create a new **public** repo named `YOUR_GITHUB_USERNAME.github.io` (replace with your actual username, e.g. `vsangaraju.github.io`).
2. Don't initialize it with a README this time — you already have the files here.

## 2. Push these files

From this folder (`GDE/Personal-Site/`), in Terminal:

```bash
cd "/Users/venkatasangaraju/GDE/Personal-Site"
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/YOUR_GITHUB_USERNAME.github.io.git
git push -u origin main
```

(If `git` prompts for login, use a GitHub Personal Access Token as the password — GitHub no longer accepts account passwords for git operations.)

## 3. Enable Pages (usually automatic for this repo name)

Go to the repo → **Settings → Pages**. Under "Build and deployment," confirm:
- Source: **Deploy from a branch**
- Branch: **main**, folder **/ (root)**

Save. Your site goes live at `https://YOUR_GITHUB_USERNAME.github.io` within a minute or two.

## 4. Before you push — fill these in

- [ ] `index.html` — replace `YOUR_GITHUB_USERNAME` and `YOUR_LINKEDIN` in the nav links (2 places)
- [ ] `posts/_template.html` — same 2 placeholders (only matters once you copy it to write a real post)

## 5. Adding a new post later

**Option A — link out** (fastest): if you're publishing on Medium/dev.to anyway, just add a new `.post` block to `index.html` (a commented-out template block is already in the file) pointing `href` at the external URL.

**Option B — write it directly on this site**: copy `posts/_template.html` to `posts/your-post-slug.html`, fill in the title/body, then add a `.post` block in `index.html` linking to `posts/your-post-slug.html` instead of an external URL.

Either way: commit and push, and the live site updates within a minute.

## 6. Portfolio page (optional, not built yet)

The nav links to `portfolio.html`, which doesn't exist yet — either remove that nav link for now, or say the word and I'll build a portfolio page matching this same style (projects, certifications, GDE progress, etc.).
