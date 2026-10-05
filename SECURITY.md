# Security policy

## Supported versions

Only the [latest release](https://github.com/wlt1920/AxisNex/releases/latest) receives fixes. Please update before reporting.

## Reporting a vulnerability

Please **don't** report security problems in a public issue.

1. Go to the repository's **Security** tab and choose **Report a vulnerability**. This opens a private report that only the maintainer can see.
2. If that option isn't available, open a normal issue titled **"Security contact request"** without any details, and you'll be given a private way to send the report.

Helpful details: the AxisNex version, what an attacker could do, and the steps to reproduce it.

AxisNex is maintained by one person in their spare time. Reports are read and taken seriously, but there are no guaranteed response times or bounties.

## Scope

In scope:

- The AxisNex app and installer published in this repository's releases.
- The update mechanism (release manifest, download and SHA-256 check).

Out of scope — please report these to their own projects:

- [HidHide](https://github.com/nefarius/HidHide), [HIDMaestro](https://github.com/hifihedgehog/HIDMaestro), [hidusbf](https://github.com/LordOfMice/hidusbf) and the other components listed in [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt).
- Copies of AxisNex downloaded from anywhere other than this repository or [wltziff.nl](https://wltziff.nl).

## Verifying downloads

The installer is not code-signed. Every release lists the installer's SHA-256; compare it before installing:

```powershell
Get-FileHash .\AxisNex-…-Setup.exe
```

More about administrator rights, drivers and the update check: [README → Security](README.md#security).
