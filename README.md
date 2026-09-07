# karmidd.github.io

Personal pages. Plain static HTML, no dependencies and no build step for the
pages themselves.

The root, <https://karmidd.github.io>, is a directory listing every page on the
site. It is **generated** — `index.html` is written by `build-index.js` and
overwritten on every push, so don't edit it by hand.

## Adding a page

Make a folder with an `index.html` and push:

```
mkdir notes && $EDITOR notes/index.html    # → karmidd.github.io/notes/
```

That's the whole process. CI regenerates the root directory, so the new page
shows up at `/` on its own. Give each page a `<title>` and a description — the
directory reads its rows from them:

```html
<title>Notes</title>
<meta name="description" content="What the page is, in one line">
```

The description is the text shown next to the path; without one the directory
falls back to the title.

To preview the directory locally, run `node build-index.js`.

## The other option: a separate repo

Any repo of yours can publish its own page at `karmidd.github.io/<repo-name>` —
create it, then turn on Settings → Pages → Deploy from a branch. Worth it when a
project has its own code and history. For small standalone pages, a folder here
is less work, and it gets listed in the directory automatically.

## Notes

- `.nojekyll` skips Jekyll processing, so files are served exactly as committed.
- Pages deploys from the default branch on every push; a build takes ~1 minute.
- The training page stores checked-off exercises in `localStorage`. It's
  per-device, and clears itself each day.
