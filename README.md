# Lidl prijzen dashboard

## Setup (once)
1. Create a new **public** repo on github.com, e.g. `lidl-dashboard`.
2. Upload all files from this folder into it (or `git push` them).
3. Repo → Settings → Pages → Source: "Deploy from a branch" → branch `main`, folder `/root` → Save.
   Your dashboard will be live at `https://<your-username>.github.io/lidl-dashboard/`.
4. Repo → Settings → Actions → General → under "Workflow permissions" select
   **Read and write permissions** → Save. (Needed so the workflow can commit `data.json` back.)
5. Repo → Actions tab → click "Scrape Lidl prices" → "Run workflow" → Run.
   Wait ~1-2 minutes, then refresh your GitHub Pages URL.

## Editing your shopping list
Edit `shopping_list.json` in the repo (product name in Dutch + quantity), commit,
then re-run the workflow (or wait for the daily 06:00 UTC run).

## If a product shows "niet gevonden"
Open the finished workflow run → Artifacts → download `debug-output` → send the
relevant .html file back to Claude to fix the matching logic for that product.
