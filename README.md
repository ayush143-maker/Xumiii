# Xumiii

A single-page interface for short-lived conversations, with a join-code flow, message area, and voice and video call controls. This repository describes the client interface; session authentication, call signalling, and message storage or deletion depend on the server-side implementation and deployment.

## Open locally

Open `index.html` in a modern browser, or run:

    python -m http.server 8000

Visit http://localhost:8000.

## Working on the experience

Keep join and conversation states clear, with helpful feedback when a room cannot be reached. Verify backend access controls, retention, and call infrastructure before describing the service as private or temporary.