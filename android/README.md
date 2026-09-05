# Android App Support

This directory is the Kalmix support index for Android field apps used with SCOUT PRO and SCOUT receivers. It mirrors the connection categories in the [Kalmix Integrations Hub](https://www.kalmixtech.com/pages/integrations), while making the level of Kalmix verification explicit.

## Choose a Connection Path

### NTRIP Inside

The field app connects to the receiver and runs its own NTRIP correction client. The receiver, corrections, and field workflow stay in the same app, so no separate correction-provider app is required.

Choose this path when the app itself can manage the receiver and corrections—for example, a direct mapping workflow in SW Maps.

### Mock Location

A provider app manages corrections and shares the corrected position with Android through Mock Location. A compatible field app can then use that Android location as its position source.

Choose this path when the app you want to use does not manage NTRIP itself, but can consume Android's corrected location. It is a two-app workflow: the provider app holds the receiver connection; the field app uses the shared location.

## Reading the Support Status

- **Verified** — Kalmix has tested a specific receiver, app, Android, and correction-path combination. A public version, date, and quickstart are shown where they have been published.
- **Listed — not independently verified** — the app appears in the current Kalmix Hub under its applicable connection path, but this repository does not yet contain a Kalmix test record for a specific combination. It is a support-resource listing, not a deployment guarantee.
- **Quickstart available** — a published Kalmix reference with the tested setup, acceptance signals, and boundaries.

Only the two quickstarts below currently publish the full test environment and date. We will add that evidence to other verified entries as their support references are prepared.

## NTRIP Inside Apps

| App | Kalmix status | Support path | Documentation |
|---|---|---|---|
| **SW Maps** | **Verified** | Direct app connection + built-in NTRIP | [Quickstart — Android 16 · 2026-08-11](sw-maps/) |
| **Field GNSS** | **Verified** | Direct app connection + in-app NTRIP | Support reference in preparation |
| **GNSS Master** | **Verified** | Direct app connection + in-app NTRIP; can also enable Mock Location for compatible apps | [Quickstart — Android 15 · 2026-08-20](gnss-master/) |
| **Lefebure NTRIP Client** | **Verified** | In-app NTRIP correction workflow | Support reference in preparation |
| **Locus GIS** | **Verified** | Direct app connection + in-app NTRIP | Support reference in preparation |

## Mock Location Apps

| App | Kalmix status | Support path | Documentation |
|---|---|---|---|
| **Carry Map** | **Verified** | Corrected Android location through Mock Location | Support reference in preparation |
| **Google Earth** | Listed — not independently verified | Corrected Android location through Mock Location | See [Integrations Hub](https://www.kalmixtech.com/pages/integrations) |
| **Google Maps** | **Verified** | Corrected Android location through Mock Location | Support reference in preparation |
| **QField** | **Verified** | Corrected Android location through Mock Location | Support reference in preparation |
| **Avenza Maps** | Listed — not independently verified | Corrected Android location through Mock Location | See [Integrations Hub](https://www.kalmixtech.com/pages/integrations) |
| **Gaia GPS** | Listed — not independently verified | Corrected Android location through Mock Location | See [Integrations Hub](https://www.kalmixtech.com/pages/integrations) |
| **CalTopo** | Listed — not independently verified | Corrected Android location through Mock Location | See [Integrations Hub](https://www.kalmixtech.com/pages/integrations) |
| **Fulcrum** | Listed — not independently verified | Corrected Android location through Mock Location | See [Integrations Hub](https://www.kalmixtech.com/pages/integrations) |
| **Locus Map** | **Verified** | Corrected Android location through Mock Location | Support reference in preparation |
| **Mapit GIS** | **Verified** | Corrected Android location through Mock Location | Support reference in preparation |
| **Mergin Maps** | **Verified** | Corrected Android location through Mock Location | Support reference in preparation |
| **OCAD** | Listed — not independently verified | Corrected Android location through Mock Location | See [Integrations Hub](https://www.kalmixtech.com/pages/integrations) |
| **Global Mapper Mobile** | Listed — not independently verified | Corrected Android location through Mock Location | See [Integrations Hub](https://www.kalmixtech.com/pages/integrations) |

## Shared Connection Baseline

The two published quickstarts connect the SCOUT receiver over USB Serial at **115200 bps** and use the selected app's NTRIP client to send corrections to the receiver. In a Mock Location workflow, the provider app remains responsible for the USB connection and corrections; the field app consumes the shared Android location instead.

## Shared Limits

- Android USB Serial access is exclusive: close other GNSS utilities before opening a receiver in the selected provider app.
- The phone powers the receiver during these USB-C workflows. Battery behavior varies by device and must be checked for long sessions.
- Mock Location is an Android bridge, not proof that every app version, phone, tablet, or Android release will accept corrected location.
- These references do not establish iOS compatibility. Keep NTRIP credentials, precise coordinates, serial numbers, and customer logs out of public issues and commits.

[← Back to verified integrations](../)
