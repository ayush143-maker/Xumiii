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

## Asset and loading review checklist

These are review steps, not verified results or measured performance claims:

- Inspect `index.html` for local image, audio, and font references and verify that each local path points to an existing file. The repository root lists `README.md` and `index.html`; check the actual referenced paths rather than assuming that no nested or externally hosted assets exist.
- Review any local media for file size and suitability at its intended display size. Consider replacing unnecessarily large assets with appropriately sized versions, and keep only files that are actually used.
- Confirm that the Google Fonts request for Manrope is intentional. Check readability if the external font request is unavailable, and avoid requesting styles the page does not use.
- PeerJS 1.5.4 is loaded from jsDelivr. Confirm that this CDN script is an intentional dependency for the page's peer-related behavior, and review whether that behavior requires the external request. Do not treat the script reference alone as evidence that calls or signalling work.
- Check that external font and script requests are appropriate for the intended deployment and that local path changes remain aligned with references in `index.html`.

## Accessibility review checklist

These are future review checks, not claims that accessibility has been verified:

- Use the keyboard to move through the join-code flow, message area, and voice and video call controls. Check that each available field and action can be reached and operated, and that focus order is predictable.
- Check that a visible focus indicator remains easy to identify on every focused field, link, and control.
- Check that the join-code field, message entry, and call controls have meaningful labels and instructions. Check that call and message feedback is not conveyed only by a change in colour or icon.
- Check text, control, and focus-indicator contrast against the page backgrounds, including message content and any status feedback.
- Review any images or media that convey information and check their alternatives in `index.html`; do not assume decorative elements need descriptive text.
- If call indicators, transitions, or other effects animate, check the page with reduced motion enabled and whether motion can be reduced without losing important status information.

## Editing the page

Update visible copy and presentation in `index.html`. The page references Google Fonts and loads PeerJS from a CDN; preserve those URLs unless you are intentionally changing the corresponding dependency. No separate asset files are listed at the repository root, so inspect the HTML for existing asset references before adding or replacing images. Keep any relative `src` or `href` paths aligned with the files they reference.

Before describing the service as private or temporary, verify backend access controls, data retention, and call infrastructure.