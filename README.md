# Xumiii

A single-page HTML interface for short-lived conversations. `index.html` presents a join-code flow, a message area, and voice and video call controls. The page alone does not verify session authentication, call signalling, or message storage and deletion; those depend on the server-side implementation and deployment.

## Open locally

Open `index.html` in a browser, or serve the project folder over HTTP:

```sh
python -m http.server 8000
```

Then visit <http://localhost:8000>. After editing `index.html`, reload the page and review the join and conversation states, including feedback when a room cannot be reached.

## Editing the page

Update visible copy and presentation in `index.html`. The page references Google Fonts and loads PeerJS from a CDN; preserve those URLs unless you are intentionally changing the corresponding dependency. Before adding or replacing images, inspect the HTML for existing asset references: no separate asset files are listed at the repository root. Keep any relative `src` or `href` paths aligned with the files they reference.

Before describing the service as private or temporary, verify backend access controls, data retention, and call infrastructure.