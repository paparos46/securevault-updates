# SecureVault — Public Updates Channel

This is the **public static update delivery site** for the SecureVault Windows prototype.
The application source remains in the separate **private** `paparos46/securevault` repository.

Only public website content and (eventually) separately approved, cryptographically
signed release metadata and Windows installers belong here. **Never commit secrets,
passwords, payment data, master passwords, private publisher signing keys,
user vaults, Chrome profiles, or private project source code.**

## Current status: NOT ACTIVATED

- [Website](https://paparos46.github.io/securevault-updates/)
- [Service status](https://paparos46.github.io/securevault-updates/health.json)
- The `update.json` file intentionally **does not exist** yet. This means there is
  **no live software update** until a pinned publisher public key and signed
  installer are provisioned.
- The currently installed v0.15.0 Windows client cannot automatically update until
  the one-time signed-feed bootstrap client is manually installed.

## Initial GitHub Pages setup

On this repository: **Settings → Pages → Build and deployment → Deploy from a branch**,
choose **main** and **/(root)**; click **Save**. Only after GitHub successfully
publishes the site can these links be used.

## Release integrity

The future client will check the pinned Ed25519 publisher signature on the exact
installer URL/version/hash/size, download using HTTPS, rehash the installer before
launching it, and require the user's approval. The offline publisher private
key must **never** be stored in any GitHub repository. Publish final installer
bytes first, and only then publish the signed `update.json`.

No production-grade security audit has been performed; SecureVault is a TEST app.
