# AI Touch Machine v0.1

A standalone, local-first radial PWA hosted under `/touch-machine/` in the Ownership Engine Alpha GitHub Pages repository.

## Deploy

1. Commit the `touch-machine/` folder to the repository's Pages-published branch (currently `main`).
2. Keep the repository's existing root `index.html` unchanged.
3. Wait for GitHub Pages to publish.
4. Open: `https://alps0n.github.io/ownership-engine-alpha-site/touch-machine/`
5. In iPhone Safari, tap Share → Add to Home Screen → Add.

## v0.1 features

- Six radial controls: Capture, Think, Create, Execute, Memory, Verify.
- Captured intentions stored in IndexedDB on this device/browser profile.
- Local rule-based interpretation; no cloud request.
- Local draft preparation.
- Execute is a guarded placeholder: it records intent for future Shortcut integration and does not run an external action.
- Structural record check and JSON export.
- Service-worker app-shell caching for offline reopening after the first successful load.

## Acceptance tests

1. Open the URL in Safari over HTTPS; the status changes from STARTING to READY.
2. Tap Capture, enter a sentence, and tap Save locally; latest intention appears.
3. Tap Think; status becomes interpreted-local and a local interpretation appears.
4. Tap Create; a draft appears and no external action is sent.
5. Tap Execute and confirm; status becomes awaiting-shortcut-configuration. Verify no app action or message was sent.
6. Tap Memory; the saved intention appears.
7. Tap Verify; log reports PASS and number of local records.
8. Tap Export JSON; a JSON backup is downloaded.
9. Add to Home Screen and launch from its icon.
10. After first successful load and service-worker installation, enable Airplane Mode and relaunch; the app shell should open. IndexedDB records should remain on the same browser profile.

## Data and limitations

- Data is stored in IndexedDB for this PWA origin on this device. It is not synchronized to Ownership Engine Alpha or iCloud.
- Browser/site data clearing can erase records. Export backups regularly.
- v0.1 does not connect a cloud AI provider, execute Shortcuts, access other apps, or provide cryptographic tamper evidence.
- Cloud AI, native Shortcuts handoff, stronger verification, and explicit permissions are future milestones.
