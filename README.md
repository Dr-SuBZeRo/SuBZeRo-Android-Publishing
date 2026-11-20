<div align="center">

# SuBZeRo — Android Publishing

**Independent Android application publishing, release engineering and store compliance.**

[![Developer](https://img.shields.io/badge/Developer-SuBZeRo-245A83?style=flat-square)](https://github.com/Dr-SuBZeRo)
[![License](https://img.shields.io/badge/License-Apache--2.0-blue?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](https://developer.android.com/)

</div>

Central operations repository for preparing, validating and distributing SuBZeRo's Android applications. Application source code remains in its own repository; this repository holds shared publishing policy, checklists, store guidance and release-engineering templates.

## Principles

- Free applications: no advertisements, subscriptions or in-app purchases.
- Privacy-first and offline-first by default.
- No mandatory account or cloud service for core functionality.
- Open-source licensing and third-party notices are maintained transparently.
- One application is prepared and released at a time.
- Releases are tested, traceable and cryptographically verifiable.

## Application portfolio

| Application | Repository | Publishing status |
|---|---|---|
| MargiQ | [Repository](https://github.com/Dr-SuBZeRo/MargiQ) | First candidate — audit required |
| CashQ | [Repository](https://github.com/Dr-SuBZeRo/CashQ) | Planned |
| WalletQ | [Repository](https://github.com/Dr-SuBZeRo/WalletQ) | Planned |
| StockQ | [Repository](https://github.com/Dr-SuBZeRo/StockQ) | Planned |
| ClinicQ | [Repository](https://github.com/Dr-SuBZeRo/ClinicQ) | Planned |

These are planning statuses, not claims of store approval or production readiness.

## Distribution channels

| Channel | Role | Delivery |
|---|---|---|
| [Google Play](https://play.google.com/console/) | Primary mainstream store | AAB |
| [F-Droid](https://f-droid.org/docs/) | FOSS repository and independent build | Source-based repository build |
| [GitHub Releases](https://github.com/Dr-SuBZeRo) | Official direct downloads and release archive | Developer-signed APK |
| [IzzyOnDroid](https://izzyondroid.org/) | Additional FOSS repository, subject to eligibility | Developer-signed APK |
| [Obtainium](https://github.com/ImranR98/Obtainium) | User-controlled installation/update client | Tracks upstream releases |
| Samsung Galaxy Store / Huawei AppGallery / Uptodown | Optional additional reach | Store-specific submission |

Obtainium is an installation/update client, not an app store. Each channel has independent eligibility, review, signing and policy requirements.

## Repository guide

- [Publishing strategy](docs/PUBLISHING_STRATEGY.md)
- [Store requirements](docs/STORE_REQUIREMENTS.md)
- [Release process](docs/RELEASE_PROCESS.md)
- [Signing and security](docs/SIGNING_SECURITY.md)
- [Privacy policy guide](docs/PRIVACY_POLICY_GUIDE.md)
- [Release checklist](templates/RELEASE_CHECKLIST.md)
- [Store listing template](templates/STORE_LISTING.md)
- [Changelog template](templates/CHANGELOG.md)
- [Application registry](apps/)

## Release workflow

1. Select one application and complete its readiness audit.
2. Confirm package ID, versioning, licence, dependencies and permissions.
3. Validate tests, lint, release build and real-device behaviour.
4. Prepare store metadata and accurate privacy disclosures.
5. Sign and verify artifacts using the channel-specific process.
6. Publish the GitHub release and checksums.
7. Submit to selected stores and track review outcomes.
8. Verify installation, upgrades and data migration after publication.

## Security

Never commit keystores, signing passwords, upload keys, service-account files, API tokens or personal data. Use protected secrets or secure local storage. See [Signing and security](docs/SIGNING_SECURITY.md).

## Licence

Original documentation and configuration in this repository are licensed under the [Apache License 2.0](LICENSE), unless a file or third-party component states otherwise. Each application repository retains its own licence and notices.
