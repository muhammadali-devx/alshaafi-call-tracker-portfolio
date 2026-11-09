# Architecture Overview

This document describes the Android-side structure at a high level. It intentionally omits production URLs, request credentials, employee identifiers, and private backend details.

## Main components

| Component | Responsibility |
|---|---|
| `MainActivity` | Main application entry point and primary app experience |
| `LoginScreen` | Employee sign-in interface |
| `CallMonitorService` | Monitors call-log changes and coordinates local processing/synchronization |
| `CallRecordStore` | Persists call records locally, classifies call activity, and tracks pending sync state |
| `CallSyncWorker` | Background call-record synchronization |
| `AutoThankYouSms` | Schedules eligible thank-you SMS work |
| `CourierStatusSmsWorker` | Processes queued courier-status SMS work |
| `BootReceiver` | Handles the configured device-boot event for app background behavior |

## Data flow

1. Employee signs in through the app.
2. The app obtains call-log data when the required Android permission is granted.
3. Call records are normalized/classified and saved locally.
4. A background worker uploads pending records to the authenticated backend.
5. Successfully synchronized records are marked as synced locally; retryable failures can be retried.

## Platform considerations

- Android runtime permissions and device/OEM background-execution behavior affect availability.
- Call-log and SMS access are sensitive capabilities and must be disclosed and used only with appropriate consent and authorization.
- The backend is a separate private service and is not included in this portfolio repository.
