# SportvoedingDirect Theme - Setup Instructions

## What's Been Done

1. **.gitignore** – Added to exclude `.shopify/`, `node_modules/`, and environment files
2. **Git** – Local commits are up to date
3. **Auth started** – GitHub and Shopify authentication were initiated (see below)

---

## Complete These Authentication Steps

> **If the codes below have expired**, run `gh auth login` and `shopify theme push --unpublished` again to get new codes.

### 1. GitHub Authentication

1. Open: **https://github.com/login/device**
2. Enter this code: **77D5-4D74** (or use a new code from `gh auth login`)
3. Authorize the GitHub CLI in your browser

### 2. Shopify Authentication

1. Open: **https://accounts.shopify.com/activate-with-code**
2. Enter this code: **BSDL-SFDG** (or use a new code from `shopify theme push --unpublished`)
3. Log in to your SportvoedingDirect Shopify store and approve

---

## Run These Commands After Auth

Use a terminal in `C:\Users\Adrian\Documents\GitHub\SvD-2.0-Vernieuwd`:

### A. Publish to GitHub

```powershell
gh repo create SvD-2.0-Vernieuwd --public --source=. --remote=origin --push
```

If the repo already exists:

```powershell
git remote add origin https://github.com/YOUR_USERNAME/SvD-2.0-Vernieuwd.git
git push -u origin main
```

### B. Push Theme to Shopify (Unpublished)

```powershell
shopify theme push --unpublished
```

Use `--store sportvoedingdirect` if you have multiple stores.

### C. Connect GitHub to Shopify (Optional – Two-Way Sync)

1. In **Shopify Admin**: Online Store → Themes
2. Click **Add theme** → **Connect from GitHub**
3. Install the Shopify GitHub app if asked
4. Choose the `SvD-2.0-Vernieuwd` repo and `main` branch
5. Connect the branch to your unpublished theme

---

## Development Commands

| Command | Description |
|--------|-------------|
| `shopify theme dev` | Start a local dev preview with live reload |
| `shopify theme push` | Upload theme changes to Shopify |
| `shopify theme pull` | Download theme from Shopify |
| `shopify theme publish` | Publish the current theme as live |

---

## Store URL

If the store subdomain differs from `sportvoedingdirect`, use:

```powershell
shopify theme push --unpublished --store YOUR-STORE-NAME
```
