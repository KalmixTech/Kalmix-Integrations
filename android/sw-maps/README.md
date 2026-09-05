# SW Maps + SCOUT Series — Direct Field Mapping

**A verified one-app field-mapping workflow** for a Kalmix SCOUT PRO or SCOUT receiver over USB-C. SW Maps owns the receiver connection, correction feed, and map view—there is no position-bridge app in this tested path.

[Open the complete SW Maps setup guide](https://www.kalmixtech.com/blogs/integrations/scout-with-sw-maps) &nbsp;·&nbsp; [Back to Android integrations](../)

## What This Verifies

```text
SCOUT PRO / SCOUT → USB-C → Android 16 → SW Maps USB Serial → built-in NTRIP client → receiver → RTK Fix on the map
```

## When SW Maps Is the Better Fit

Choose SW Maps when your work begins and ends on its map: connect the receiver, bring in corrections, and assess the resulting RTK position in one workspace. It is the simpler of these two workflows when you do **not** need to send corrected location into another Android app.

### Our Take

For a focused mapping session, the one-app design is the appeal. There are fewer handoffs to check, and the map itself gives the immediate field-facing acceptance signal. The trade-off is deliberate: this verified path does not create an Android Mock Location bridge for other apps.

## Tested Setup

| Component | Tested value |
|---|---|
| Receivers | SCOUT PRO / SCOUT |
| App | SW Maps 3.1.1.0 |
| Host | Android 16 |
| Receiver connection | USB Serial, 115200 bps |
| Correction path | SW Maps built-in NTRIP client → receiver |
| Success signal | RTK Fix visible on the SW Maps map |
| Last verified | 2026-08-11 |

## Quick Configuration

1. Connect the receiver to the Android device through its integrated USB-C cable and allow SW Maps to access the USB device.
2. In SW Maps, select **USB Serial** and set the receiver baud rate to **115200**.
3. Add the NTRIP profile supplied by your correction provider, then start the correction connection.
4. Move to an open-sky location and confirm live receiver data, an active correction path, and **RTK Fix** on the map.

## Map Acceptance

- SW Maps shows live receiver position data after the USB Serial link opens.
- The NTRIP connection is active and corrections are being delivered to the receiver.
- The map shows **RTK Fix**; in the tested view this appears as a green position marker without an accuracy circle.

## Limits and Safety Notes

- This reference covers **Android 16 over USB Serial** only. The iOS build was not tested.
- For shared USB and power constraints, see the [Android connection baseline](../#shared-connection-baseline).
- Keep provider credentials, precise locations, and customer field logs out of public issues and commits.

For screenshots, field checks, troubleshooting, and the complete configuration sequence, [open the official SW Maps guide](https://www.kalmixtech.com/blogs/integrations/scout-with-sw-maps).
