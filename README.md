# Xumiii

A single-page HTML interface for short-lived conversations. `index.html` presents a join-code flow, a message area, and voice and video call controls. The page alone does not verify session authentication, call signalling, or message storage and deletion; those depend on the server-side implementation and deployment.

## Open locally

Open `index.html` in a browser, or serve the project folder over HTTP:

```sh
python -m http.server 8000
```

Then visit <http://localhost:8000>. After editing `index.html`, reload the page and review the join and conversation states, including feedback when a room cannot be reached.

Before describing the service as private or temporary, verify backend access controls, data retention, and call infrastructure.