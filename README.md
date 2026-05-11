# Advanced SRX Firewall Bootcamp

Internal training website for the **Advanced SRX Firewall Bootcamp** — a 3-day instructor-led, lab-heavy program for HPE APJ Systems Engineers covering advanced Juniper SRX security features.

## Overview

| | |
|---|---|
| **Dates** | May 26–28, 2026 · or June 2–4, 2026 (tentative) |
| **Location** | HPE Singapore — 1 Depot Close, Singapore 109841 |
| **Format** | In-person · Hands-on labs (JCL and CloudShare) |
| **Seats** | Limited to 10 engineers |
| **Audience** | Internal · APJ Systems Engineers |

## Curriculum

- **Day 1** — JCL Lab, SE Tools, High Availability (Chassis Cluster & MNHA), Tenant Systems (LSYS & TSYS)
- **Day 2** — NAT, Routing & VPN (IPsec)
- **Day 3** — Advanced Services (AppSecure, UTM, Content Security) & Capstone Challenge

> **June 2 notice:** A fire drill at HPE Depot Close affects the morning of June 2. Students join morning sessions remotely from the hotel via video conference (JCL lab exercise provided). Return to classroom from 1:00 PM.

## Repository Structure

```
srx-bootcamp/
├── index.html        # Landing / overview page
├── bootcamp.html     # Full bootcamp page (agenda, prereqs, venue, registration)
├── netlify.toml      # Netlify deployment config
└── README.md
```

## Viewing Locally

No build step required — open either HTML file directly in a browser:

```bash
open index.html
# or
open bootcamp.html
```

## Deployment

The site is deployed via [Netlify](https://netlify.com). Any push to the `main` branch triggers an automatic redeploy. The `netlify.toml` sets the publish directory to the repo root.

## Making Updates

All content — agenda, dates, venue, registration contacts — lives directly in the HTML files as inline data. Key sections to edit:

- **Dates / seats / format** — `bootcamp.html`, the `spec-card` aside in the hero section
- **Agenda** — `bootcamp.html`, the `AGENDA_DAY1 / DAY2 / DAY3` JavaScript arrays
- **Prerequisites** — `bootcamp.html`, the `#prereqs` section
- **Venue & hotel** — `bootcamp.html`, the `#venue` section
- **Registration contacts** — `bootcamp.html`, the `.reg-contact` div in the `#register` section

## Contacts

| Role | Name | Email |
|---|---|---|
| Bootcamp organizer | Kelly Brazil | — |
| Registration | Andy Leung | aleung@hpe.com |
| Registration | Victor Deng | jiang.deng@hpe.com |

---

*Internal use only · HPE APJ Systems Engineering*
