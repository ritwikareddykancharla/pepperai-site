# Welcome Flow Masterclass

Source repository for the Revenue Systems Academy "Welcome Flow Masterclass" course.

## Cursor Cloud specific instructions

This is a **fully static, dependency-free website** — vanilla HTML/CSS/JS with no package manager, build system, tests, or linting configured.

- Structure: `index.html` is the entry point and contains the inline render logic. Course text lives in `course.js` (`window.L`), and email example images are base64 WebP data URIs in `images0.js`–`images4.js` (`window.I`). `style.css` holds all styles. Files in `assets/` are source/reference material and are not loaded by the running app.
- There is **nothing to install, build, lint, or test** — no `package.json`, lockfile, `Makefile`, or CI. Do not add a build step unless explicitly asked.
- Run it by serving the repo root with any static file server, e.g. `python3 -m http.server 8000` from `/workspace`, then open `http://localhost:8000/index.html`. `python3` and `node` are both preinstalled. The app also works when opening `index.html` directly via `file://` since all assets are local.
- No fixed port, env vars, database, backend, or auth. Script load order (`images*.js` → `course.js` → inline render) is already handled by `<script>` ordering in `index.html`.
- Verification is manual/visual: confirm the sidebar module list, the "Course home" grid, individual lesson pages (with embedded email images), and Previous/Next navigation all render.
