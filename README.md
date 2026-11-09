# AL SHAAFI Call Desk — Android Call Tracking Portfolio

**Developer:** Muhammad Ali  
**Project type:** Android application  
**Status:** Portfolio overview of a privately maintained business application

## Overview

AL SHAAFI Call Desk is an Android application developed to support employee call-desk operations. It captures call activity on an enrolled Android device, stores call records locally, and synchronizes pending records with the connected business backend.

The project is built with **Kotlin** and **Jetpack Compose**. Background tasks support synchronization and selected customer-notification workflows.

> **Portfolio note:** This repository contains project documentation only. The production application source code, backend implementation, customer records, credentials, and internal business configuration are intentionally not published.

## Key capabilities

- Employee sign-in and caller-specific session handling.
- Incoming, outgoing, missed, and rejected call record handling.
- Local call-record storage and classification.
- Background call-log synchronization with the business backend.
- Employee-oriented call activity and reporting support.
- Scheduled/background work for selected SMS notification workflows.
- Android UI built with Jetpack Compose.

Feature availability can depend on Android version, runtime permissions, device settings, and the connected backend.

## Technology stack

- **Language:** Kotlin
- **UI:** Jetpack Compose, Material 3
- **Platform:** Android
- **Background processing:** Android services, WorkManager, boot receiver
- **Local storage:** SQLite via Android SQLite APIs
- **Networking:** HTTP/JSON API communication
- **Build system:** Gradle (Kotlin DSL)

## High-level architecture

1. The Android app authenticates an employee and maintains a caller-specific session.
2. Android call-log access is used to read eligible call records, subject to user-granted permission.
3. Records are classified and persisted locally to avoid losing pending data during temporary connectivity issues.
4. Background synchronization sends pending records to the connected backend.
5. Background workers support selected customer SMS workflows where enabled and permitted.

See [`docs/architecture.md`](docs/architecture.md) for a concise component overview.

## Privacy and permissions

Call-tracking software handles sensitive personal information. The production app requests Android permissions for features such as call-log access, contacts, SMS, notifications, camera, and location. Permissions should be requested only when the corresponding feature is needed, explained clearly to users, and handled in accordance with applicable law and platform policies.

This public portfolio repository does **not** contain real call logs, phone numbers, customer information, authentication tokens, API credentials, production endpoints, or the production source code.

## Screenshots

Screenshots may be added after removing employee names, phone numbers, tokens, customer information, and any internal business data.

## About the developer

Muhammad Ali is a software developer working with Android development, business applications, API integrations, and workflow automation.

- **LinkedIn:** [Muhammad Ali](https://www.linkedin.com/in/muhammad-ali-23b640293/)
- **Email:** muhammadalirai860@gmail.com

---

*This is a portfolio description of a privately maintained project. It is not a distribution of the production application or its source code.*
