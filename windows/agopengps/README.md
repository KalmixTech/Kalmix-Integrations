# AgOpenGPS + SCOUT Series — RTK Position Input for Windows

**A verified Windows positioning workflow** for a Kalmix SCOUT PRO or SCOUT receiver. AgIO opens the receiver's USB serial port, sends Network NTRIP corrections back over that same port, and passes position to AgOpenGPS.

[Open the complete AgOpenGPS setup guide](https://www.kalmixtech.com/blogs/integrations/scout-with-agopengps) &nbsp;·&nbsp; [Back to Windows support](../)

## What This Verifies

```text
Network NTRIP service → AgIO on Windows 10 ⇄ USB Serial ⇄ SCOUT PRO / SCOUT
                                                          ↓ position
                                                     AgOpenGPS → RTK Fix
```

This reference verifies the RTK **position input** path under open sky. It does not verify an entire autosteer or vehicle-control system.

## About the Software

AgOpenGPS is open-source guidance and section-control software for farm machinery. AgIO is its companion communication layer: it opens the GNSS serial port, connects to the NTRIP service, returns corrections to the receiver, and passes the receiver position to AgOpenGPS.

### When This Workflow Fits

Choose this workflow when the task is to give an AgOpenGPS setup a live RTK position from a receiver connected directly to a Windows computer or tablet. The useful checkpoint is simple: AgIO has a live receiver link and correction stream, while AgOpenGPS reports **RTK Fix**.

### Our Take

The AgIO split makes the communication path visible: you can separately inspect the COM-port link, NTRIP session, correction bytes, and RTK status before working on the rest of a machine. That clarity is valuable, but it is also the boundary of this reference. A vehicle still needs its own steering hardware, sensing, control logic, tuning, and safe field validation.

## Tested Setup

| Component | Tested value |
|---|---|
| Receivers | SCOUT PRO / SCOUT |
| AgOpenGPS | 6.8.5 |
| AgIO | v1.0.0 |
| Host | Windows 10 |
| Receiver connection | USB Serial, 115200 bps |
| Correction path | Network NTRIP → AgIO → receiver over the same USB serial port |
| Success signal | RTK Fix in AgOpenGPS and `Quality: RTK fix` in AgIO System Data |
| Last verified | 2026-08-20 |

## Quick Configuration

1. Connect the receiver directly to the Windows host through its integrated USB-C cable.
2. In **Device Manager**, find the COM port that appears with the receiver. In **AgIO → Connect GPS**, select that port at **115200** bps; leave the separate **RTCM** port empty for this serial path.
3. In AgIO's NTRIP settings, enter the provider's caster, port, mount point and credentials. On the Position tab, select **Use GPS Fix**, set **SERIAL** on and **UDP** off.
4. Save the configuration as an AgIO profile. Reopen it once at the desk to confirm the COM port, baud rate and correction settings were retained.
5. Under open sky, start AgOpenGPS, turn NTRIP on, and confirm a live receiver position before judging RTK status.

## Position Acceptance

- The AgIO receiver icon is connected and its byte counter is moving.
- NTRIP reports **Listening** and the sent-byte value changes from dashes to a number, showing corrections are being written to the receiver.
- AgOpenGPS shows **RTK Fix** and AgIO System Data reports **Quality: RTK fix**.

## Scope and Safety Notes

- This reference covers **Windows 10**, AgOpenGPS 6.8.5, AgIO v1.0.0, and the USB serial path stated above. It does not establish support for other Windows releases or software versions.
- It does **not** validate heading, roll, steering controllers, wheel-angle sensors, actuators, vehicle control, tuning, or operation on a moving machine.
- Windows can change the receiver's COM number after reconnection. Check Device Manager before changing other settings.
- Keep NTRIP credentials, precise locations, serial numbers, and customer machine logs out of public issues and commits.

For screenshots, troubleshooting, and the complete configuration sequence, [open the official AgOpenGPS guide](https://www.kalmixtech.com/blogs/integrations/scout-with-agopengps).
