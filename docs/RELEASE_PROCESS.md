# Android Release Process

## 1. Prepare

1. Select one application from the publishing queue.
2. Confirm the default branch is clean and all intended changes are committed.
3. Review open issues and resolve or explicitly defer release blockers.
4. Confirm package ID, version name and monotonically increasing version code.
5. Review permissions, manifest, network behaviour and third-party SDKs.
6. Review licence notices and dependency licences.
7. Update documentation and changelog.

## 2. Validate

Typical Gradle tasks (availability varies by project):

```bash
./gradlew testDebugUnitTest
./gradlew lintDebug
./gradlew assembleRelease
./gradlew bundleRelease
```

Use tasks actually configured in the project. Test critical workflows on physical devices, including offline behaviour and upgrade from the previous supported version.

## 3. Freeze release source

- Review final diff.
- Commit release changes.
- Create an annotated tag, for example `v1.2.0`.
- Record full commit SHA.
- Never move or reuse a published release tag.

## 4. Build and sign

- Build from the tagged commit in a controlled environment.
- Generate AAB for Google Play and the appropriate APK for direct distribution.
- Use the documented signing identity for the intended channel.
- Never put keystore files or passwords in the repository.
- Verify package ID, version, signature and certificate fingerprint.

## 5. Verify artifacts

Linux/macOS:

```bash
sha256sum app-release.apk app-release.aab > SHA256SUMS.txt
```

Windows PowerShell:

```powershell
Get-FileHash .\app-release.apk -Algorithm SHA256
Get-FileHash .\app-release.aab -Algorithm SHA256
```

Record the result and verify it again after downloading the published artifact.

## 6. Publish

1. Publish GitHub Release notes and direct APK when appropriate.
2. Submit AAB to Google Play testing.
3. Submit to F-Droid only after policy and build eligibility checks.
4. Submit to IzzyOnDroid only after its policy and code-provenance review.
5. Check Obtainium discovery against the public GitHub release.
6. Submit to optional stores only when the expected audience justifies the work.

## 7. Post-release verification

- Install from each approved channel on a clean device.
- Verify first launch, permissions and offline behaviour.
- Verify upgrade from previous version.
- Check crash reports and user feedback.
- Confirm release links, checksums and privacy policy.
- Record store status and release date in the app registry.

## Rollback

Do not assume stores permit downgrades. If a release is defective, stop staged rollout or halt further distribution, prepare a higher version code with a fix, and communicate data risks. Preserve affected artifacts and logs for investigation.
