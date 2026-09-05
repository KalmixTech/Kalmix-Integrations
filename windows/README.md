# Windows Support

Verified Kalmix workflows for Windows hosts. These pages record the tested receiver, software, connection and correction path; use the linked official Guide for the full setup and screenshots.

| Software | Choose it when | Tested environment | Last verified | Quick reference |
|---|---|---|---|---|
| **AgOpenGPS 6.8.5 + AgIO v1.0.0** | You need RTK position input for an AgOpenGPS field workflow. | Windows 10 · SCOUT PRO / SCOUT · USB Serial 115200 bps · Network NTRIP | 2026-08-20 | [Open quickstart](agopengps/) |

## Shared Limits

- Windows assigns the receiver a COM port. Check Device Manager after reconnecting; the port number can change when you use another host port.
- Only one program can hold the receiver's serial port. Close TRACE, serial terminals, and other GNSS utilities before opening the port in AgIO.
- This reference verifies the **position input layer** only. Heading, roll, steering controller hardware, wheel-angle sensing, actuators, vehicle control, tuning, and safe field testing are separate system-level work.

[← Back to verified integrations](../)
