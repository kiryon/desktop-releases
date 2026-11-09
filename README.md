# Kiryon Desktop releases

Installers of **Kiryon** for macOS, Windows and Linux. Kiryon is a
product of KUTBU, LLC. Download from [kiryon.com/download](https://kiryon.com/download)
or from the [latest release](https://github.com/kiryon/desktop-releases/releases/latest).

This repository holds release files only (installers, update metadata,
checksums and SBOMs). It contains no source code.

## Verify a download

Each release lists `SHA256SUMS-<os>.txt`:

```bash
shasum -a 256 Kiryon-mac-arm64.dmg        # macOS
sha256sum Kiryon-linux-amd64.deb          # Linux
Get-FileHash Kiryon-win-x64-setup.exe     # Windows (PowerShell)
```

Releases here are immutable: once published, their files cannot be changed,
and GitHub signs a release attestation. Check that a download belongs to a
published release with the GitHub CLI:

```bash
gh release verify-asset v1.0.0 Kiryon-mac-arm64.dmg -R kiryon/desktop-releases
```

macOS builds are signed with an Apple Developer ID (**KUTBU, LLC**) and
notarized by Apple. Windows builds are Authenticode-signed with the publisher
**KUTBU, LLC**. The first Windows builds are unsigned (Windows shows "Unknown
publisher"); they update themselves to signed builds once signing is enabled.

## Security

See [SECURITY.md](SECURITY.md).
