<div align="center">

<img src="https://raw.githubusercontent.com/KalmixTech/Kalmix-Hardware/main/Assets/KALMIX-Logo.png" alt="Kalmix Logo" width="160">

# Verified GNSS Integrations

*Quick references for tested Kalmix receiver, software, and correction paths.*

[Integrations Hub](https://www.kalmixtech.com/pages/integrations) &nbsp;·&nbsp; [Hardware Resources](https://github.com/KalmixTech/Kalmix-Hardware) &nbsp;·&nbsp; [Contact Support](https://www.kalmixtech.com/pages/contact)

</div>

---

## Published Quickstarts

| Platform | Software | Best for | Last verified | Quick reference |
|---|---|---|---|---|
| Android | **SW Maps 3.1.1.0** | Direct field mapping in one app | 2026-08-11 | [Open SW Maps quickstart](android/sw-maps/) |
| Android | **GNSS Master 1.5.0.0** | Bridging corrected location to compatible Android apps | 2026-08-20 | [Open GNSS Master quickstart](android/gnss-master/) |

SW Maps keeps receiver control, corrections, and the map in one place. GNSS Master is the better fit when the receiver needs to serve another Android app through Mock Location. Both references use USB Serial and NTRIP, but they solve different field workflows.

## How to Use This Repository

- **Verified** means the exact receiver, app, host OS, connection path, correction path, and success signal stated on the page were tested together. It does not mean every device, software release, or feature is supported.
- These pages are fast technical references. The linked Kalmix Integration Guides remain the complete, canonical setup instructions.
- Do not commit NTRIP credentials, precise coordinates, device serial numbers, customer names, or unredacted field logs.

## Browse by Platform

| Platform | Available references |
|---|---|
| [Android](android/) | SW Maps and GNSS Master over USB Serial |

For the complete software directory and related field workflows, visit the [Kalmix Integrations Hub](https://www.kalmixtech.com/pages/integrations).
