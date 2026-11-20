# SuBZeRo Android Multi-Store Publishing Strategy

## Confirmed decisions

- Developer identity: **SuBZeRo**.
- Google Play account: personal.
- Budget: pay Google's one-time registration fee; prefer free distribution and automation elsewhere.
- Cadence: prepare and release one application at a time.
- Product principles: free, privacy-first and offline-first by default.
- Source of truth: each application's own GitHub repository.
- This repository: shared publishing policy, templates and release engineering.

## Distribution priorities

### Primary
1. **Google Play** — mainstream Android discovery and managed updates.
2. **GitHub Releases** — upstream source, direct APKs, release notes and checksums.
3. **F-Droid** — FOSS repository and source-build process, only when the app and dependencies meet current policy.

### Secondary
4. **IzzyOnDroid** — additional repository; check current inclusion and code-provenance requirements.
5. **Obtainium** — user-controlled installation/update client that can follow GitHub releases. It is not an app store.

### Optional expansion
6. Samsung Galaxy Store.
7. Huawei AppGallery.
8. Uptodown.
9. Other reputable stores only after reviewing ownership, update integrity, signing, privacy and policies.

Do not submit everywhere automatically. Assess eligibility and operational effort per application.

## One-app-at-a-time policy

An app enters the publishing queue only after:
- Feature scope is stable and release blockers are closed.
- Package ID is confirmed and protected from accidental changes.
- Unit tests, lint and release build pass.
- Critical workflows are tested on physical devices.
- Backup/export and migration behaviour are understood.
- Permissions and network use are justified.
- Dependency and licence inventory is reviewed.
- Privacy policy, Data safety answers and store listing are accurate.
- Signing and recovery procedures are documented.

**MargiQ is the first candidate, subject to a fresh production-readiness audit.** This is not a claim that it is already ready or approved.

## Release record

For each release, record application name, repository, package ID, version name/code, Git tag and commit SHA, build toolchain, test results, artifact filenames, SHA-256 checksums, signing certificate fingerprints, store submission dates, review status and listing URLs.

Never include private keys, passwords, access tokens or personal information.

## Channel compatibility

Android updates require compatible package identity and signing certificates. Google Play App Signing, direct APK signing and F-Droid repository signing can produce different certificates. Maintain a verified update-compatibility matrix per app. Do not promise cross-store updates unless tested. For incompatible channels, publish a backup/export and migration guide before users switch.

## Automation principles

- Use GitHub Actions for repeatable checks and artifact creation.
- Keep CI separate from publishing credentials.
- Build from reviewed tags.
- Pin or control action versions.
- Use least-privilege secrets and protected environments.
- Require manual approval for production publishing.
- Retain a manual release path.

## Official policy references

Re-check policies at every submission:
- Google Play: https://support.google.com/googleplay/android-developer/
- F-Droid: https://f-droid.org/docs/
- F-Droid inclusion: https://f-droid.org/docs/Inclusion_Policy/
- IzzyOnDroid: https://izzyondroid.org/
- Obtainium: https://github.com/ImranR98/Obtainium
- Android app signing: https://developer.android.com/studio/publish/app-signing
