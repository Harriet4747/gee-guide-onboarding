# Gee Guide — onboarding product

This repo is the shareable Gee Guide onboarding product: the sanitized
curriculum, download, and setup a new person sees. It is generated from the
author's local guide store and pushed here automatically on each publish, so the
author edits once and every install updates from the same URL.

Installs fetch the product at the raw URL:

    https://raw.githubusercontent.com/Harriet4747/gee-guide-onboarding/main/published.json

`published.json` is machine-generated and sanitized — no private roster, ops, or
assessment internals. Do not hand-edit it; edit the source guide and republish.

## Point an install at this product

A partner or onboardee runs their own Gee Guide Brick (they need gee-code and the
Terminal installed). To make their Guide serve this product instead of an empty
local store, drop `guide_config.json` into the Brick root at
`~/.gee/bricks/gee-guide/guide_config.json`:

    {
      "published_url": "https://raw.githubusercontent.com/Harriet4747/gee-guide-onboarding/main/published.json"
    }

That file is included here as a copy-ready template. Then start the Brick with
`python3 ~/.gee/bricks/gee-guide/server.py` — the Guide fetches this product and
caches the last good copy for offline use. The author's own install leaves
`guide_config.json` absent and keeps serving its live local store.
