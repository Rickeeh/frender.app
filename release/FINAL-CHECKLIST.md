# fRender Free 1.0.0 — Final Release Checklist (macOS)

Target DMGs (no ZIP):
- `release/mac/fRender-Free-1.0.0-mac-arm64.dmg`
- `release/mac/fRender-Free-1.0.0-mac-x64.dmg`

## 1) Build signed free (arm64/x64)
- Run signed Free builds from the release commit.

## 2) Notarize
- Submit both mac builds to Apple notarization.

## 3) Staple
- Staple notarization tickets to each `.app` and final `.dmg`.

## 4) Required checks
Run for each architecture build:

```bash
codesign --verify --deep --strict --verbose=2 fRender.app
spctl --assess --type execute --verbose=4 fRender.app
xcrun stapler validate fRender.app
```

## 5) Upload DMGs
- Place final notarized DMGs in:
  - `release/mac/fRender-Free-1.0.0-mac-arm64.dmg`
  - `release/mac/fRender-Free-1.0.0-mac-x64.dmg`

## 6) Activate links on site
- Links are already prewired in `index.html` to the two files above.
- Final activation is publishing the DMGs at those exact paths.
