# GitHub repository settings

Paste these into the repository's **About** panel (the gear icon next to "About" on the repo's main page). This file is just notes for you; you don't need to upload it.

**Repository name:** `siritap`

**Description** (350 characters max):

> Use an Apple TV Siri Remote as a trackpad, scroll wheel and voice keyboard for your Mac. Tap zones, momentum and ring scrolling, gestures, per-app buttons, and voice typing with on-device speech and voice commands. Free, menu bar, macOS 14+.

**Website:** `https://siritap.leet.ae`

**Topics:**
`macos` `siri-remote` `apple-tv-remote` `menu-bar-app` `swiftui` `trackpad` `remote-control` `voice-typing` `dictation` `speech-recognition` `accessibility` `bluetooth`

**Tick:** Releases. Untick Packages, and Deployments if it appears.

**Social preview** (Settings → General → Social preview): upload `screenshots/general.png`.

## Creating the release

1. Releases → **Draft a new release**.
2. Tag: `v0.2`. Title: `Siritap 0.2`.
3. Paste the contents of `RELEASE_NOTES_0.2.md` as the description.
4. Attach `Siritap-0.2.dmg`.
5. Publish.

## What to upload to the repo

```
README.md
PRIVACY.md
docs/            (the website; also upload it to your server)
screenshots/
  icon.png  general.png  pointer.png  taps.png  scrolling.png
  gestures.png  buttons.png  apps.png  voice.png
.github/ISSUE_TEMPLATE/bug_report.md
```

Don't commit the DMG to the repo; attach it to the release.

## The website (siritap.leet.ae), on your own server

Upload the contents of `docs/` as the site's web root:

```
index.html                  the home page
download/index.html         forwards to the current DMG
downloads/Siritap-0.2.dmg   the app
img/                        icon and screenshots
```

Every download button on the page points to `/download/`, and that page forwards to the DMG. So for a new version you:

1. Upload `downloads/Siritap-0.3.dmg` (keep the old one, so links people already shared still work).
2. In `download/index.html`, change `0.2` to `0.3` in its three places.
3. Change "Version 0.2" on the home page.

Server notes:
- Any static web server works (nginx, Apache, CloudPanel's static site). No PHP or database.
- Serve `.dmg` as `application/x-apple-diskimage`. nginx and Apache usually do this already.
- DNS in Cloudflare: an `A` record named `siritap` pointing to the server. Proxied (orange cloud) is fine. Because every version has its own file name, Cloudflare's cache never serves an old app.
- Turn on HTTPS (Let's Encrypt in CloudPanel, or Cloudflare's certificate).

GitHub links on the page (View on GitHub, Report a problem, privacy notes) still go to the repo: replace `GITHUB_USER` in `index.html` with your username.
