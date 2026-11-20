<div align="center">

# SuBZeRo — Android Publishing

**Independent Android application publishing, release engineering and store compliance.**

[![Developer](https://img.shields.io/badge/Developer-SuBZeRo-245A83?style=flat-square)](https://github.com/Dr-SuBZeRo)
[![License](https://img.shields.io/badge/License-Apache--2.0-blue?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](https://developer.android.com/)

</div>

A central operations repository for preparing, validating and distributing SuBZeRo's Android applications across Google Play, F-Droid, GitHub Releases and other suitable distribution channels.

This repository contains publishing policy, reusable checklists, store guidance, application release records and CI templates. Application source code remains in its own repository.

## Principles

- Free applications: no advertising, subscriptions or in-app purchases.
- Privacy-first and offline-first by default.
- No mandatory account, registration or cloud service for core functionality.
- Open-source licensing and third-party notices are maintained transparently.
- One application is prepared and released at a time.
- Release artifacts are traceable, tested and cryptographically verifiable.

## Application portfolio

| Application | Repository | Publishing status |
|---|---|---|
| MargiQ | [Dr-SuBZeRo/MargiQ](https://github.com/Dr-SuBZeRo/MargiQ) | First candidate — audit required |
| CashQ | [Dr-SuBZeRo/CashQ](https://github.com/Dr-SuBZeRo/CashQ) | Planned |
| WalletQ | [Dr-SuBZeRo/WalletQ](https://github.com/Dr-SuBZeRo/WalletQ) | Planned |
| StockQ | [Dr-SuBZeRo/StockQ](https://github.com/Dr-SuBZeRo/StockQ) | Planned |
| ClinicQ | [Dr-SuBZeRo/ClinicQ](https://github.com/Dr-SuBZeRo/ClinicQ) | Planned |

Status is an operational planning indicator, not a claim that an application is approved by any store.

## Distribution channels

| Channel | Role | Package / delivery |
|---|---|---|
| [Google Play](https://play.google.com/console/) | Primary mainstream store | Android App Bundle (AAB) |
| [F-Droid](https://f-droid.org/docs/) | FOSS repository with independent build process | Source-based repository build |
| [GitHub Releases](https://github.com/Dr-SuBZeRo) | Official direct downloads and release archive | Developer-signed APK |
| [IzzyOnDroid](https://apt.izzysoft.de/fdroid/) | Additional FOSS repository, subject to its policy | Developer-signed APK |
| [Obtainium](https://github.com/ImranR98/Obtainium) | User-controlled discovery and updates from upstream sources | Usually GitHub release APK |
| Samsung Galaxy Store | Additional device ecosystem | Store-specific submission |
| Huawei AppGallery | Additional device ecosystem | Store-specific submission |
| Uptodown | Optional alternative distribution | Store-specific submission |

Obtainium is an installation/update client, not an app store. F-Droid builds and signs applications under its own repository process. Each store has independent eligibility, review, signing and policy requirements.

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
2. Confirm application ID, versioning, licence, dependency inventory and permissions.
3. Validate the release build, tests, lint and real-device behaviour.
4. Prepare store metadata, privacy disclosures and screenshots.
5. Sign and verify release artifacts using the documented channel-specific process.
6. Publish the GitHub release and checksums.
7. Submit to the selected stores and track review outcomes.
8. Verify installation, upgrade and data migration behaviour after publication.

See [Release process](docs/RELEASE_PROCESS.md).

## Security

Never commit keystores, signing passwords, upload keys, service-account JSON files, API tokens, private certificates or personal data. Use protected GitHub Actions secrets or local secure storage. Read [Signing and security](docs/SIGNING_SECURITY.md) before configuring release automation.

## Licence

This repository's original documentation and configuration are licensed under the [Apache License 2.0](LICENSE), unless a file or third-party component states otherwise. Application repositories retain their own licence and notices.
