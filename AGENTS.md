# Benson Revenue — Static Site

## Overview
A static HTML marketing site for "Benson Revenue" (lead reactivation for premium detailers). No backend, no build step, no dependencies. Six pages: `index.html`, `dpa.html`, `earnings.html`, `imprint.html`, `privacy.html`, `terms.html`.

## Running in the sandbox
- Served by `nginx:alpine` via `docker-compose.base44.yml` on host port 3000.
- A custom `nginx.conf` runs the worker as `root` because the repo directory has restrictive (700) permissions that the default `nginx` user cannot traverse.
- Source is bind-mounted read-only; edits to HTML files are immediately visible (no rebuild needed, just reload the preview).
- No external credentials or secrets required.

## Verification
- `curl -s -o /dev/null -w "%{http_code}" http://localhost:3000/` should return 200.
- All six HTML pages should return 200.
