# Signing, Secrets and Release Security

## Non-negotiable rules

- Never commit keystores, private keys, upload keys, signing passwords, service-account JSON, access tokens or recovery codes.
- Never paste secrets into issues, pull requests, logs or chat.
- Never use debug signing for public releases.
- Restrict release credentials to the smallest possible set of maintainers and workflows.
- Back up signing material securely and test restoration.

## Signing roles

### Google Play
Google Play App Signing separates the app-signing key held by Google from the upload key used to authenticate uploads. Understand which key signs user-delivered APKs and record its SHA-256 certificate fingerprint in a secure operational record.

### Direct GitHub distribution
Use a protected upstream release key for directly distributed APKs. Updates require compatible package identity and signing lineage.

### F-Droid
F-Droid builds and signs repository APKs under its own infrastructure. These APKs may not update an installation signed by the developer or Google Play. Treat F-Droid as a separate update channel unless a verified signing arrangement says otherwise.

### IzzyOnDroid
Follow its current upstream signing and metadata requirements. Verify the certificate and update behaviour before publishing.

## Channel compatibility matrix

Verify this matrix with real installations for every application.

| Installed from | Update from | Assumption |
|---|---|---|
| Google Play | Google Play | Expected, subject to Play signing |
| GitHub | GitHub | Expected if signing identity is unchanged |
| Obtainium tracking GitHub | GitHub | Uses upstream APK/signature |
| F-Droid | F-Droid | Repository-managed signing |
| GitHub | Google Play | Do not assume; verify certificates |
| Google Play | GitHub | Do not assume; verify certificates |
| F-Droid | Google Play/GitHub | Usually separate signing; migration may require backup and reinstall |

## GitHub Actions secrets

Example secret names if release automation is introduced:
- `ANDROID_KEYSTORE_BASE64`
- `ANDROID_KEYSTORE_PASSWORD`
- `ANDROID_KEY_ALIAS`
- `ANDROID_KEY_PASSWORD`

These are examples only. Configure them only after reviewing the workflow. Prefer protected environments and required reviewers for production signing. Never print secret values or commit decoded keystore files.

## Verification

Use Android SDK Build Tools:

```bash
apksigner verify --verbose --print-certs app-release.apk
```

Record certificate SHA-256 fingerprints securely. Investigate unexpected changes before distribution.

## Incident response

If a key or credential may be exposed:
1. Stop releases using the affected credential.
2. Revoke or rotate credentials where supported.
3. Determine whether store key reset/recovery is available.
4. Assess impact on installed users and update continuity.
5. Document the incident without exposing secrets.
