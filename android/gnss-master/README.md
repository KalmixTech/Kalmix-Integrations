# GNSS Master + SCOUT Series — Position Bridge & Diagnostics

**A verified receiver-bridge workflow** for a Kalmix SCOUT PRO or SCOUT receiver over USB-C. GNSS Master can manage the receiver and corrections, expose RTK status, and optionally provide corrected Android location to a compatible third-party app.

[Open the complete GNSS Master setup guide](https://www.kalmixtech.com/blogs/integrations/scout-with-gnss-master) &nbsp;·&nbsp; [Back to Android integrations](../)

## What This Verifies

```text
SCOUT PRO / SCOUT → USB-C → Android 15 → GNSS Master USB Serial → NTRIP client → receiver → RTK status
                                                                  └→ Android Mock Location for compatible apps
```

## When GNSS Master Is the Better Fit

Choose GNSS Master when the receiver needs to support another Android app, rather than when the mapping work lives entirely in the receiver-control app. Its key role in this reference is the bridge: it holds USB Serial, feeds corrections to the receiver, and can expose the corrected position through Android Mock Location.

### Our Take

GNSS Master makes the connection state and RTK mode explicit, which is useful when diagnosing a receiver workflow before passing location downstream. The extra capability also brings an important boundary: Mock Location is an Android mechanism, not a promise that every third-party app will consume corrected location.

## Tested Setup

| Component | Tested value |
|---|---|
| Receivers | SCOUT PRO / SCOUT |
| App | GNSS Master 1.5.0.0 |
| Host | Android 15 |
| Receiver connection | USB Serial, 115200 bps |
| Correction path | GNSS Master NTRIP client → receiver |
| Position bridge | Android Mock Location for compatible apps |
| Success signal | Receiver connected; correction input active; RTK Float or RTK Fix in GNSS Status |
| Last verified | 2026-08-20 |

## Quick Configuration

1. Connect the receiver through its integrated USB-C cable and allow GNSS Master to open for the USB device.
2. In **GNSS Receiver Connection**, select **USB Serial**, choose the detected device, set **115200** bps, and connect.
3. In **Correction Input**, create an NTRIP Client profile with the details supplied by your correction provider, then start the correction connection.
4. Enable **Android Mock Location** only when a compatible third-party Android app needs the corrected system location.
5. Under open sky, confirm the receiver connection and correction input before checking **RTK Float** or **RTK Fix** in GNSS Status.

## Receiver and Bridge Acceptance

- GNSS Master reports that the USB Serial receiver connection is open.
- The correction input is connected and data is delivered toward the receiver.
- GNSS Status reports **RTK Float** or **RTK Fix**; use **RTK Fix** as the final acceptance signal when field conditions and correction coverage permit.

## Limits and Safety Notes

- This reference covers **Android 15 over USB Serial** only; it does not validate iOS or other Android releases.
- Android Mock Location is a bridge for compatible third-party apps, not proof that every Android app can consume corrected positioning.
- For shared USB and power constraints, see the [Android connection baseline](../#shared-connection-baseline).
- Keep provider credentials, precise locations, device serial numbers, and customer logs out of public issues and commits.

For screenshots, troubleshooting, and the complete configuration sequence, [open the official GNSS Master guide](https://www.kalmixtech.com/blogs/integrations/scout-with-gnss-master).
