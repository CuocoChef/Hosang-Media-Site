# Hosang Media — Website

A self-contained, static rebuild of hosangmedia.com. No build tools, no dependencies to install — just three files that any static host (like GitHub Pages) can serve directly.

## Files

- `index.html` — homepage (hero, who we serve, projects filmstrip, services, stats, contact)
- `about.html` — "About Curtis" page (bio, clients, project highlights, awards, skills)
- `style.css` — shared stylesheet used by both pages

All three files must stay in the **same folder** — the pages link to `style.css` and to each other using relative paths (`style.css`, `about.html`, `index.html`), not full URLs.

## Hosting this on GitHub Pages (free)

1. Create a public GitHub repo (e.g. `hosang-media-site`)
2. Upload `index.html`, `about.html`, and `style.css` to the **root** of that repo — not inside a subfolder
3. Go to **Settings → Pages**
4. Under "Build and deployment," set **Source** to `Deploy from a branch`
5. Set branch to `main`, folder to `/ (root)`, then **Save**
6. Wait 1–2 minutes, then refresh Settings → Pages — it should show a green checkmark and a link like:
   `https://<your-username>.github.io/<repo-name>/`

## If you get a 404 on the Pages URL

Check these in order — they cover the vast majority of GitHub Pages 404s:

- **Files are nested one folder too deep.** If you uploaded a zip or dragged a folder, you might end up with `hosang-media-site/hosang-media-site/index.html` instead of the files sitting directly in the repo root. Open your repo on GitHub and confirm `index.html` is visible immediately on the main repo page, not inside a subfolder.
- **The repo is Private.** Free GitHub Pages requires a Public repo.
- **It just hasn't finished deploying yet.** Check the "Actions" tab in your repo — there should be a "pages build and deployment" run. Wait for it to show a green check, not a spinner or red X.
- **Wrong URL casing/format.** The live URL is always lowercase username + repo name + trailing slash: `https://yourusername.github.io/repo-name/`
- **Source wasn't saved.** Go back to Settings → Pages and re-confirm branch is `main` and folder is `/root`, then hit Save again even if it looks already set.

## Pointing your real domain (hosangmedia.com) at this

Once the `github.io` URL works:

1. In your domain's DNS settings, add an **A record** for `@` pointing to each of:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
2. Add a **CNAME record** for `www` pointing to `yourusername.github.io`
3. In GitHub → Settings → Pages, add `hosangmedia.com` as the custom domain, then check **Enforce HTTPS** once it verifies

DNS changes can take a few minutes up to 24 hours to fully propagate.
