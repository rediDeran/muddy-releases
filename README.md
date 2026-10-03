# muddy releases

Signed installers and the update manifest for **muddy**, a markdown editor for
Windows.

This repository contains **no source code**. It exists because muddy's source
repository is private, and a private repository's release assets cannot be
downloaded by the in-app updater — the updater sends no credentials, by design,
so that no token ever ships inside the application.

## What is here

Every release carries two files:

- `muddy_<version>_x64-setup.exe` — the installer. Installs per-user and needs
  no administrator.
- `latest.json` — the manifest muddy reads to decide whether an update exists.

Both are signed. muddy checks the signature against a public key compiled into
the application and refuses anything that does not match it.

## Installing

Download the `.exe` from the [latest release](../../releases/latest) and run it.
It is not code-signed, so Windows SmartScreen will ask once — *More info* →
*Run anyway*.

Already have muddy? Update it from the ↻ button in the title bar instead.

## Publishing

Releases are built, signed and pushed here by CI in the source repository.
Nothing is committed to this repository by hand.
