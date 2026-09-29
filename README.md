# PingChat — Android Preview Build

PingChat is a Flutter mobile application being developed for private and group conversations, with planned MEA token payments through the PingPay wallet. This repository distributes the **Android APK build and release information only**. It does not contain the Flutter source code.

> **Current public build:** `v0.1.0` (development preview)  
> **Target public launch:** 1 November 2026

## Current development status

The `v0.1.0` build represents the base Flutter application architecture and initial chat interface. The screens demonstrate the intended experience; they do not demonstrate completed messaging or payment functionality.

| Area | Status in this build |
| --- | --- |
| Flutter Android application and chat interface | Base build and screens developed |
| Account creation without phone number or email | Planned; end-to-end application status to be confirmed |
| One-to-one messaging | Not yet implemented in the app |
| Group messaging | Not yet implemented in the app |
| Self-managed OpenIM server | Built for intended direct and group messaging integration |
| PingPay platform authentication API | Available; PingChat app integration not yet confirmed |
| PingPay deep-link support | Added to PingPay backend and application; not yet integrated into PingChat |
| Wallet connection and MEA transfer in chat | Not yet integrated into PingChat |
| Group event donations | Planned; not implemented |
| On-chain transactions from PingChat | Not yet implemented or tested in the app |

The intended account model gives each user a unique ID without requiring a phone number or email address. Users are intended to choose a chat retention period between 1 and 24 hours. These are product requirements and should not be interpreted as features demonstrated by this preview build.

## Planned launch scope

The planned public release on **1 November 2026** is intended to support:

1. One-to-one chat.
2. Group chat.
3. MEA token transfers initiated in a chat and signed through PingPay.

Voice calls, video calls, and friend discovery are outside the initial launch scope. Group event donations are an intended feature, but their release date is not yet confirmed. Sponsorship functionality is being clarified with the team.

## Intended architecture

```text
PingChat Flutter app
  ├── PingChat account / unique user ID
  ├── Self-managed OpenIM server → direct and group messages
  └── PingPay platform API → authentication
       └── PingPay app via deep link / MWA → wallet review and signature
            └── MEA transaction on Solana
```

The payment sequence above is the **planned integration**, not a working flow in `v0.1.0`. The intended user flow is to initiate an MEA transfer in PingChat, open PingPay to review and sign it, submit it to Solana, and display the result back in PingChat. The precise deep-link/MWA handoff and transaction response handling remain subject to integration and testing.

For the planned donation feature, participants in a group would contribute MEA to an offline event created for that group. This feature has not been implemented in the preview build.

## Download and install

1. Open this repository's **Releases** page.
2. Select the `v0.1.0` release and download its attached `.apk` asset.
3. Open the APK on an Android device and follow the installation prompt. Android may ask you to permit installation from the app used to open the file.
4. Launch PingChat to inspect the current preview screens.

The release asset filename and minimum supported Android version should be listed in the release notes after they are verified. There is no iOS build in this repository. Install only release assets published by the project team.

## Versioning and release notes

Public builds are published as GitHub Releases using version tags such as `v0.1.0`. Each release should include its APK, build date, a short description of what is actually functional, known limitations, and ideally a SHA-256 checksum. The release tag identifies the distributed binary; it does not imply that all planned `1.0.0` features are complete.

### `v0.1.0` — initial preview

- Established the Flutter Android application build.
- Added initial chat interface screens and base application structure.
- Prepared the application for subsequent OpenIM and PingPay integration.
- Direct and group messaging, wallet connection, MEA transactions, and donations are not yet functional in this build.

## Evidence for reviewers

Reviewers may use the APK and the following project materials to assess progress.

## Source code and support

This public repository is a **binary distribution and progress record**. The private application source code is not included. The APK is an installable Android package; distributing it does not publish the original Flutter project, although packaged applications can be inspected or reverse engineered.
