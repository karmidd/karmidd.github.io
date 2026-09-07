# karmidd.github.io

Personal pages. Plain static HTML, no dependencies and no build step.

| Path | What it is |
| --- | --- |
| [`/`](https://karmidd.github.io) | Index linking to everything below |
| [`/training/`](https://karmidd.github.io/training/) | Gym schedule and diet targets |

## Adding a new page

Make a folder with an `index.html` in it and push. The folder name becomes the
URL:

```
mkdir notes && $EDITOR notes/index.html    # → karmidd.github.io/notes/
```

Then add a card to the root `index.html` pointing at `/notes/` so it's reachable
from the front page.

## The other option: a separate repo

Any repo of yours can publish its own page at `karmidd.github.io/<repo-name>` —
create the repo, then turn on Settings → Pages → Deploy from a branch. Worth it
when a project has its own code and history. For small standalone pages, a
folder in this repo is less work: one repo, one deploy, live in about a minute.

## Notes

- `.nojekyll` skips Jekyll processing, so files are served exactly as committed.
- Pages deploys from the default branch on every push; a build takes ~1 minute.
- The training page stores checked-off exercises in `localStorage`. It's
  per-device, and clears itself each day.
