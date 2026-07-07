# Advanced SRX Firewall Bootcamp

Internal training website for the **Advanced SRX Firewall Bootcamp** — a 2-day instructor-led program for HPE India Systems Engineers covering advanced Juniper SRX security features.

## Overview

| | |
|---|---|
| **Session 1** | Aug 4–5, 2026 — HPE India, Bangalore |
| **Session 2** | Aug 12–13, 2026 — HPE India, New Delhi |
| **Format** | In-person · Lectures and discussions |
| **Seats** | Limited per session |
| **Audience** | Internal · HPE India Systems Engineers |

## Curriculum

- **Day 1** — SRX Packet Walkthrough, Security Services, High Availability (MNHA), Tap Mode POC, MIST Security Assurance, Multi-tenant Support (TSYS & LSYS), Sizing & BOM, SE Tools
- **Day 2** — User Firewall & Security Director, SRX Automation (MCP), CGNAT on MX and SRX, Cloud & Virtualization (vSRX & cSRX), Advanced Security Threat, EVPN / Secure Data Center Architecture, CSDS Scale Out Architecture & Wrap-up

## Repository Structure

```
srx-bootcamp/
├── index.html        # Full bootcamp page (agenda, prereqs, venue, registration)
├── netlify.toml      # Netlify deployment config
└── README.md
```

## Viewing Locally

No build step required — open the HTML file directly in a browser:

```bash
open index.html
```

## Deployment

The site is deployed via [Netlify](https://netlify.com). Any push to the `main` branch triggers an automatic redeploy. The `netlify.toml` sets the publish directory to the repo root.

## Making Updates

All content — agenda, dates, venue, registration contacts — lives directly in `index.html` as inline data. Key sections to edit:

- **Dates / seats / format** — the `spec-card` aside in the hero section
- **Agenda** — the `AGENDA_DAY1 / DAY2` JavaScript arrays
- **Prerequisites** — the `#prereqs` section
- **Venues** — the `#venue` section
- **Registration contacts** — the `.reg-contact` div in the `#register` section

## Contacts

| Role | Name | Email |
|---|---|---|
| Bootcamp organizer | Kelly Brazil | — |
| Registration | Andy Leung | aleung@hpe.com |
| Registration | Victor Deng | jiang.deng@hpe.com |

---

*Internal use only · HPE APJ Systems Engineering*
