# Xumiii

A single-page interface for short-lived conversations. Visitors can use the join-code flow and view the message area and voice and video call controls. This repository describes the client interface; session authentication, call signalling, and message storage or deletion depend on the server-side implementation and deployment, so the interface alone does not verify those capabilities.

## Open locally

Open `index.html` in a modern browser, or serve the project folder over HTTP:

    python -m http.server 8000

Then visit http://localhost:8000.

## Working on the experience

Keep the join and conversation states clear, with helpful feedback when a room cannot be reached. Verify backend access controls, retention, and call infrastructure before describing the service as private or temporary.