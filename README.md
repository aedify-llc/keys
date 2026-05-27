# Aedify public signing keys

This repository publishes Aedify's **public** signing-key material to a
stable, publicly fetchable URL via GitHub Pages:

- <https://keys.aedify.io/root.pem>

It contains only non-secret public keys plus the GitHub Pages `CNAME`.
No source, no private keys, no other artifacts live here.

## Why this repo exists

The signing keys are authored in the (private) `aedify-llc/agentic_engineering`
repo. Because that repo is private, neither `raw.githubusercontent.com`
nor GitHub Pages from it can serve an open, unauthenticated endpoint. A
signing *public* key is non-secret by design, so it is mirrored here, in
a public repo, for distribution.

The authoritative copy remains `forge/keys/root.pem` in the private
repo; the file here is a published mirror.

## Files

| File | Purpose |
|---|---|
| `root.pem` | Aedify **root** public key — the long-lived trust anchor. Customers pin this (compare its fingerprint against the out-of-band Aedify customer-comms email); the chain in each bundle walks up to it. Production ceremony-minted root. |
| `CNAME` | GitHub Pages custom-domain binding (`keys.aedify.io`). |

Per-product signing keys + their root-signed certificates ship *inside*
each customer bundle (`products/<slug>/{public.pem,certificate.json}` in
the source repo); they are not published here.

The legacy single-key `public.pem` was retired — chain-mode customers
anchor on `root.pem`, and no customer uses the single-key surface.

## Status

`root.pem` is the **production** root from the key ceremony
(`docs/KEY_CEREMONY.md`).

See `docs/KEYS_URL_MIGRATION.md` in `aedify-llc/agentic_engineering` for
the full migration plan and cutover checklist (#215 / #207-H).
