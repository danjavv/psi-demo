# PSI Demo — Private Set Intersection

An interactive, single-file walkthrough that explains **Private Set Intersection (PSI)**: how two organisations can discover their *shared* customers without revealing anything else — no raw data exchanged, no trusted third party, and no trust between the parties required.

## What it shows

A split-screen view of **Organisation A** and **Organisation B**, each holding ~100 private customer records, walking through the full protocol:

1. **Connect data** — each side connects its own customer database (read locally, never uploaded).
2. **Request & consent** — one side requests a private match (fuzzy first + last name); the other approves.
3. **Secure computation** — a real **3-round Diffie–Hellman PSI** runs step-by-step. Every message on the wire is inspectable, showing exactly what each party receives and why it can't be reversed.
4. **Result** — only the requesting side learns which of *its own* customers are shared; the other side learns nothing — not the matches, not the count, not even the overlap size.

A persistent **"Who can see what"** table tracks, live at every step, exactly what each organisation knows. Guided tips, callouts, and a "What is PSI?" explainer make it approachable for first-time viewers.

The cryptography is genuinely computed in the browser (commutative encryption via `BigInt` modular exponentiation), so the tokens you inspect are real, not mocked. All customer data is synthetic.

## Run it

It's a self-contained static file — just open it in a browser:

```bash
open index.html
```

No build step, no dependencies, no server required.

## Tech

Plain HTML / CSS / vanilla JavaScript in a single `index.html`. Fonts (Inter, JetBrains Mono) load from Google Fonts when online and fall back to system fonts offline.
