# Xumiii

**XUMi** is a single-page interface for short-lived conversations. Its current layout brings together a join-code flow, a message area, and voice/video-call controls in one place, aiming to make starting a quick conversation feel straightforward.

This repository describes the client interface. It does not, by itself, establish how sessions are authenticated, how calls are signalled, or how messages are stored and deleted. Those behaviours depend on the server-side implementation and deployment.

## Open locally

The project is a standalone HTML page. Open index.html in a modern browser, or run:

    python -m http.server 8000

Then visit http://localhost:8000.

## Working on the experience

Keep the join and conversation states clear, and provide helpful feedback when a room cannot be reached. Before describing the service as private or temporary, verify the backend's access controls, retention policy, and call infrastructure.
