# JobFill Privacy Policy (GitHub Pages)

Static, dependency-free privacy-policy page for the JobFill Chrome extension
(v1.0.0). Intended for the public repository `vasu-chukka/jobfill-privacy`,
published with GitHub Pages.

## Contents

| File                 | Purpose                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `index.html`         | The published policy page. Plain HTML + a tiny inline CSS block. No JavaScript, no external resources, no cookies, no forms. |
| `privacy-policy.md`  | Markdown source of the same policy (kept identical to the extension repository's `docs/privacy-policy.md`).                   |
| `.nojekyll`          | Empty marker file. Tells GitHub Pages to serve the files as-is instead of running them through Jekyll. Harmless if unused.    |

## Why no build system

GitHub Pages serves static files directly. The policy is a single page, so a
framework (Next.js, Astro, Vite, …) would add dependencies and risk for zero
benefit. Copy the files, enable Pages, done.

## Publish steps (manual, by the repository owner)

1. Create a new **public** repository named `jobfill-privacy` under the
   GitHub account `vasu-chukka`.
2. Copy the files from this directory into the root of that repository
   (`index.html`, `privacy-policy.md`, `.nojekyll`, `README.md`).
3. Commit and push them (e.g. to the `main` branch).
4. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from
   a branch**, branch `main`, folder `/ (root)`, **Save**.
5. After a minute or two the policy is served at
   `https://vasu-chukka.github.io/jobfill-privacy/`.

No workflow file, `CNAME`, or custom domain is required unless you later decide
to host the policy at your own domain.

## Notes

- The page works offline and can be opened directly as a local file
  (`index.html`).
- Keep `privacy-policy.md` in sync with `docs/privacy-policy.md` in the
  JobFill extension repository whenever the policy changes.
- The page contains no analytics, no tracking, no remote fonts or scripts, and
  no cookies — intentionally, matching the extension's local-first stance.
