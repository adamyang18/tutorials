# tutorials

Adam Yang's private tutorial hosting via GitHub Pages.

Each tutorial lives at `/<slug>-<6-char-suffix>/`. The random suffix makes the URL hard to guess; `robots.txt` blocks search-engine indexing. The repo source is public, but the served URLs are not discoverable.

## Add a new tutorial

```bash
cd ~/Projects/tutorials
SUFFIX=$(openssl rand -hex 3)
SLUG="my-tutorial-$SUFFIX"
mkdir "$SLUG"
cp /path/to/tutorial.html "$SLUG"/index.html
git add "$SLUG"
git commit -m "add $SLUG"
git push
# URL: https://adamyang18.github.io/tutorials/<SLUG>/
# Wait ~30-60 seconds after push for GitHub Pages to redeploy.
```

## Notes

- Files must be `index.html` to serve at the directory URL without filename.
- Single-file HTML with base64-embedded images works directly. External assets need to be committed alongside.
- 100MB hard limit per file; 1GB total repo size for Pages.
- Source is public — anything sensitive should go elsewhere.
