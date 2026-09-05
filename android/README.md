# Android Integrations

Verified Android workflows for Kalmix SCOUT PRO and SCOUT receivers. Each quickstart records one tested combination; use the linked official Guide for the full setup and screenshots.

| Software | Choose it when | Tested environment | Last verified | Quick reference |
|---|---|---|---|---|
| **SW Maps 3.1.1.0** | You want to map directly in the same app that controls the receiver and corrections. | Android 16 · SCOUT PRO / SCOUT · USB Serial 115200 bps | 2026-08-11 | [Open quickstart](sw-maps/) |
| **GNSS Master 1.5.0.0** | You need to inspect RTK state, then share corrected location with a compatible Android app. | Android 15 · SCOUT PRO / SCOUT · USB Serial 115200 bps | 2026-08-20 | [Open quickstart](gnss-master/) |

## Shared Connection Baseline

Both tested workflows connect the SCOUT receiver over USB Serial at **115200 bps** and use the selected app's NTRIP client to pass corrections to the receiver. The difference is what happens next: SW Maps uses the receiver position inside its own mapping workspace; GNSS Master can optionally pass corrected location to a compatible Android app through Mock Location.

## Shared Limits

- Android USB Serial access is exclusive: close other GNSS utilities before opening a receiver in the selected app.
- The phone powers the receiver during these USB-C workflows. Battery behavior varies by device and must be checked for long sessions.
- These references do not establish iOS compatibility or support for Android versions, phones, tablets, or app releases not listed above.

[← Back to verified integrations](../)
