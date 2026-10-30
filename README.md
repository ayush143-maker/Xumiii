# Xumiii

Xumiii is a single-page interface for short-lived, one-to-one conversations. `index.html` provides a pairing-code flow, a text-message view, and audio and video call controls. It uses PeerJS 1.5.4 for pairing and peer connections, with Google STUN servers configured for WebRTC connectivity.

## Preview locally

Open `index.html` in a browser, or serve the project folder over HTTP:

```sh
python -m http.server 8000
```

Then visit <http://localhost:8000>. Microphone and camera access require HTTPS or localhost. A browser prompt is expected; denied permissions or missing devices produce an error message.

## Pair and communicate

A host code appears after the PeerJS host opens. It contains two letters and one digit, and the Copy Code button uses clipboard access with an `execCommand` fallback. Enter a code to join; input is uppercased, non-alphanumeric characters are removed, and the field is limited to three characters. Enter submits too. A waiting host regenerates its code after five minutes if nobody joins.

A host accepts one peer connection. Additional connections receive a `full` message and are closed. Once connected, users can send text over the peer data connection. Messages display with local time formatting; the source sets no message-length limit. The message list is cleared when the session is torn down, and the page has no message-storage API or browser-storage implementation. Do not interpret this interface as providing durable history or verified deletion from any infrastructure involved in a connection.

Audio-only and video call buttons request microphone access; video also requests the user-facing camera. Incoming calls offer Accept and Decline controls. During a call, users can mute, toggle the camera, or end the call. A call that does not connect within 30 seconds is ended with a no-answer message. The active-call view shows a timer and, for video, local and remote video elements.

## Dependencies and limits

PeerJS loads from jsDelivr and Manrope loads from Google Fonts, so those resources need network access. PeerJS, STUN configuration, and an attractive join screen do not by themselves establish authentication, privacy, or a guaranteed connection. Connectivity and media permissions depend on the browser, network, and peer connection conditions. Do not use real conversation data without reviewing the relevant service and deployment behavior.

The supplied page is `index.html`; no build step is documented. After editing, test pairing, the one-peer limit, message teardown, permission errors, and call controls in the browser console and network panel.