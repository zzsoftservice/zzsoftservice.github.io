# FrameTales legal-site deployment

This directory is the single source for FrameTales's marketing, support, privacy, and
purchase-terms pages. The App also bundles the two files under `static/` plus
`assets/site.css`, so legal text changes must be made here first.

The public `/cameramark/` paths are intentionally retained after the FrameTales
(相框故事) rebrand so existing App Store and app links continue to work. The app is
published under the PixelPlay brand. The September 22, 2026 update changes branding
only; it does not change the privacy or purchase provisions.

## Verified target

- Site repository: `/Volumes/Data/gits/web/zzsoftservice_github/zzsoftservice.github.io`
- Remote: `https://github.com/zzsoftservice/zzsoftservice.github.io.git`
- Destination directory: `cameramark/`
- Expected public root: `https://zzsoftservice.github.io/cameramark/`

At the 2026-09-02 audit, the site repository was on `main` at `84611ba` and already
contained an unrelated untracked `cadreader/` directory. Never use `git add .`, clean,
reset, or another broad operation in that repository while publishing FrameTales.

## Owner-authorized publish procedure

1. Recheck the site repository status and confirm `cameramark/` is still absent or
   inspect its current contents before changing it.
2. Copy this directory to the site repository as `cameramark/`. Do not delete or
   overwrite any sibling directory.
3. Inspect `git status --short -- cameramark` and the complete FrameTales-only diff.
4. Stage only `cameramark/` with `git add -- cameramark`; verify the staged name-status
   list and `git diff --cached --check` before committing.
5. Commit and push only after the repository owner explicitly authorizes those external
   writes.
6. Verify HTTP 200 for the root, `support.html`, `static/privacy_policy.html`, and
   `static/SubscriptionTerms_AppStore.html`. Do not submit App Store metadata while any
   required URL returns 404.
