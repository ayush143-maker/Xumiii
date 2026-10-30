# Xumiii

A single-page HTML interface for short-lived conversations. `index.html` contains the visitor-facing join-code flow, message area, and voice and video call controls. The interface alone does not verify session authentication, call signalling, or message storage and deletion; those depend on the server-side implementation and deployment.

## Open locally

Open `index.html` in a modern browser, or serve the project folder over HTTP:

    python -m http.server 8000

Then visit http://localhost:8000.

## Working on the experience

Keep the join and conversation states clear, with helpful feedback when a room cannot be reached. Verify backend access controls, retention, and call infrastructure before describing the service as private or temporary.