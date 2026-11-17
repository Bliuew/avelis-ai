# Review and deployment

## Current handoff

Source base: latest main fetched at task start, `f097148`. Feature branch: `feature/connected-enterprise-ecosystem`. Main and the published website have not been changed. The branch is suitable for code review; visual/browser acceptance remains outstanding.

Backups supplied outside the repository:

- `avelis-ai-main-backup.bundle`: full main history reachable from the main ref. Restore with `git clone avelis-ai-main-backup.bundle restored-avelis`.
- `avelis-ai-main-index.backup.html`: byte-identical original published entry point.

## Manual upload when write credentials are unavailable

1. Unzip the supplied source archive into a local checkout of `Bliuew/avelis-ai`.
2. Create `feature/connected-enterprise-ecosystem` from current main. Review the base SHA first; if main has advanced, rebase the additions rather than replacing newer work.
3. Copy `index.html`, `ecosystem/`, `docs/`, `README.md`, `package.json` and `.gitignore`. Keep all existing source ZIPs and setup guide.
4. Run `npm test`. For optional DOM checks install jsdom and use the README command. Serve the repository via HTTP and complete the desktop/mobile acceptance checklist.
5. Commit, push the feature branch, and open a pull request targeting main. Include the test-results document and the remaining Card Studio asset limitation.
6. Only after review, merge through the repository's normal process. Existing GitHub Pages branch/root configuration may continue unchanged. No secrets, environment variables, npm build or new hosting platform is needed.

All links are relative and support the `/avelis-ai/` GitHub Pages base path. New applications use fragment routes, avoiding server rewrites. The root original page remains the published entry point.

## Rollback

Revert the feature commit via normal review, or restore the original entry point and remove the additive ecosystem directory. The original local storage namespace was never renamed. No production backend migration occurred.

## Private reviewer and pilot services

Preserve `__PILOT_API_BASE__` and `__PRIVACY_CONTACT_EMAIL__` until an authorized secure service is deployed. The existing form requires a valid HTTPS service and privacy-contact configuration before accepting submissions. Validate the actual backend, access policy, consent, retention and reviewer permissions before enabling. GitHub Pages cannot enforce private reviewer access.

## Preview limitation in this workspace

Managed `sites-preview` could not bind `127.0.0.1:4173` (`EPERM`). No replacement server or browser-control bypass was used. Temporary local preview configuration/build copies are ignored and excluded from the source archive. This is a source-only, unpublished review handoff.
