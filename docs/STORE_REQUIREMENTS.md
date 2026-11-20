# Store Requirements and Distribution Notes

This is an operational checklist, not a substitute for current store agreements or policies. Re-check official requirements immediately before submission.

## Google Play

- Register and verify a personal Play Console developer account.
- Complete identity, contact and any required device verification.
- Pay the one-time fee displayed by Play Console.
- New personal accounts created after 13 November 2023 are subject to Google's closed-testing requirement: at least 12 testers continuously opted in for 14 days before applying for production access. Confirm current requirements in the account dashboard.
- Prepare an Android App Bundle (AAB).
- Configure Play App Signing and back up the upload key securely.
- Complete app access, ads, content rating, target audience, Data safety and privacy policy declarations accurately.
- Provide listing text, icon, screenshots and required graphics.
- Meet current target API and technical quality requirements.
- Use testing tracks before production; consider a staged rollout.

Official resources:
- https://play.google.com/console/
- https://support.google.com/googleplay/android-developer/
- https://developer.android.com/studio/publish

## F-Droid

- Read the current Inclusion Policy.
- Confirm the app licence and every bundled or fetched dependency.
- Avoid proprietary SDKs, tracking and non-free components in the F-Droid build.
- Provide complete source and build instructions.
- Ensure source tags and build metadata correspond to the submitted release.
- Resolve network access and reproducibility concerns.
- Expect independent build, review and repository signing.
- Do not assume F-Droid APKs share the developer's signing certificate.

Official resources:
- https://f-droid.org/docs/
- https://f-droid.org/docs/Inclusion_Policy/

## GitHub Releases

- Publish from a reviewed, immutable version tag.
- Attach the signed APK, release notes and SHA-256 checksums.
- Link to source and licence.
- Include minimum Android version and device notes where relevant.
- Never attach debug builds or artifacts containing secrets.
- Download the published artifact and verify its checksum.

Official resource: https://docs.github.com/en/repositories/releasing-projects-on-github

## IzzyOnDroid

- Read current inclusion policy and submission instructions.
- Confirm app/dependency licences, metadata and APK provenance.
- Review current restrictions on AI-generated or vibe-coded code; do not assume eligibility. Document actual code provenance honestly.
- Provide stable upstream releases and matching source/tag information.
- Understand its signing and update model.

Official resource: https://izzyondroid.org/

## Obtainium

- Provide a stable public upstream release page and predictable version tags/assets.
- Ensure release asset names and version information are detectable.
- Publish checksums and release notes.
- Test update detection against actual release assets.
- Explain that Obtainium is a third-party installation/update client, not an app store or endorsement.

Official resource: https://github.com/ImranR98/Obtainium

## Samsung Galaxy Store

- Register through Seller Portal.
- Complete seller and commercial approval steps as required.
- Check device, country, content and signing requirements.
- Verify listing and update behaviour on supported devices.

Official resource: https://seller.samsungapps.com/

## Huawei AppGallery

- Register and complete developer identity verification.
- Check functionality where Google Mobile Services are absent.
- Review Huawei SDK, privacy and country-specific requirements.
- Do not add Huawei services unless there is a genuine product need.

Official resource: https://developer.huawei.com/

## Uptodown and other alternative stores

- Verify publisher account, submission terms and takedown process.
- Confirm the store distributes the exact signed artifact supplied.
- Check whether it re-signs packages or changes update behaviour.
- Review privacy, analytics, advertising and bundling practices.
- Keep GitHub Releases as the upstream source of truth.

Official resource: https://www.uptodown.com/

## Per-store approval record

For each app/store, record eligibility review date, policy URL, submission date, reviewer feedback, approval date, listing URL, package version, signing certificate fingerprint and next action.
