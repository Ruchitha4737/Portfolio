Portfolio — static site

This repository contains a static portfolio (HTML/CSS/JS). This README explains how to publish it using GitHub Pages with an automated GitHub Actions workflow that deploys the site to the `gh-pages` branch.

How it works

- The workflow `.github/workflows/gh-pages.yml` runs on every push to `main` and on manual dispatch.
- It creates a `.nojekyll` file then uses `peaceiris/actions-gh-pages` to publish the repository root to the `gh-pages` branch.
- After the workflow completes the site will be available at: `https://<your-username>.github.io/<repo-name>` (GitHub may take a minute to enable the page).

Steps to publish

1. Push this repository to GitHub (if you haven't):

```powershell
git add .
git commit -m "Add GitHub Pages workflow and README"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

2. Go to your repository on GitHub → Settings → Pages (or Pages & deployments) and confirm the site source. If you used this workflow, the publish branch should be `gh-pages` (root). If Pages doesn't show the URL immediately, wait a minute and refresh.

3. If you want a custom domain, add a `CNAME` file to the repository root (or set it in the Pages settings).

Notes & Troubleshooting

- Make sure `index.html` is at the repository root.
- The workflow uses the built-in `GITHUB_TOKEN`, so you don't need to add Secrets.
- If your site assets contain files or folders starting with an underscore, `.nojekyll` prevents GitHub Pages from running Jekyll which can strip/ignore these files.

If you'd like, I can also set up Netlify or Vercel deployment files, or change the workflow to only publish a `public/` subfolder if you prefer building into `public/` first.