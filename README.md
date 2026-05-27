# Aedify public signing keys

This repository publishes Aedify's **public** signing-key material to a
stable, publicly fetchable URL via GitHub Pages:

- <https://keys.aedify.io/public.pem>

It contains only non-secret public keys plus the GitHub Pages `CNAME`.
No source, no private keys, no other artifacts live here.

## Why this repo exists

The signing keys are authored in the (private) `aedify-llc/agentic_engineering`
repo at `forge/keys/public.pem`. Because that repo is private, neither
`raw.githubusercontent.com` nor GitHub Pages from it can serve an open,
unauthenticated endpoint. A signing *public* key is non-secret by
design, so it is mirrored here, in a public repo, for distribution.

The authoritative copy remains `forge/keys/public.pem` in the private
repo; the file here is a published mirror.

## Files

| File | Purpose |
|---|---|
| `public.pem` | Ed25519 signing public key. Customers fetch this to cross-check the `public.pem` shipped inside their bundle. |
| `CNAME` | GitHub Pages custom-domain binding (`keys.aedify.io`). |

`root.pem` (the chain root from `docs/KEY_CEREMONY.md`) will be added
here once the root key ceremony has run.

## Status

The current `public.pem` is a **development placeholder**. It will be
replaced by the ceremony-minted production key when the root key
ceremony executes. Until then, treat the published key as
non-production.

See `docs/KEYS_URL_MIGRATION.md` in `aedify-llc/agentic_engineering` for
the full migration plan and cutover checklist (#215 / #207-H).
