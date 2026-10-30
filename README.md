# Xumiii

A single-page HTML interface for short-lived conversations. `index.html` presents a join-code flow, a message area, and voice and video call controls. The page alone does not verify session authentication, call signalling, or message storage and deletion; those depend on the server-side implementation and deployment.

## Open locally

Open `index.html` in a browser, or serve the project folder over HTTP:

```sh
python -m http.server 8000
```

Then visit <http://localhost:8000>.

## Manual review checklist

Use this checklist after editing `index.html`. It describes actions to perform, not verified results.

- Open the known entry page, `index.html`, in a browser and review the initial state.
- Try the join-code flow, message area, and voice and video call controls as the page presents them. Note any feedback or unavailable behavior; do not treat the interface alone as evidence of working server-side authentication, signalling, storage, or deletion.
- Inspect the HTML's image and media references. Check that each referenced local path points to the intended file, and that external references load when available.
- Review the page at a narrow viewport and a wide viewport. Check that content, controls, and text remain visible and usable.
- If an interaction or resource depends on deployment or server-side behavior, record that as requiring separate verification rather than marking it as confirmed by a local page review.

## Editing the page

Update visible copy and presentation in `index.html`. The page references Google Fonts and loads PeerJS from a CDN; preserve those URLs unless you are intentionally changing the corresponding dependency. No separate asset files are listed at the repository root, so inspect the HTML for existing asset references before adding or replacing images. Keep any relative `src` or `href` paths aligned with the files they reference.

Before describing the service as private or temporary, verify backend access controls, data retention, and call infrastructure.