# Kibana Incident Response Dashboards

[![Made with: Kibana](https://img.shields.io/badge/Made%20with-Kibana-informational)](#)
[![Status: Active](https://img.shields.io/badge/Status-Active-success)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Overview
This project demonstrates the use of **Kibana dashboards** to analyze malware activity captured in network traffic. Multiple visualizations were created to support incident response workflows.

## Visualizations
- **Time-series graph**: Malware alerts over time
- **Table**: Top malware family names and frequency
- **Suspicious domains table**: Queried domains, source IPs, and counts
- **Proportion chart**: Strange/obfuscated URIs observed in HTTP traffic
- **Custom visualization**: Extra network behavior of interest

## Tools & Technologies
- Kibana (Elastic Stack)
- PCAP analysis (imported logs)
- Elasticsearch queries

## Repository Structure
```
.
├── README.md
├── assets/                 # logos/banners used in README
├── docs/                   # extra notes, methodology, write-ups
├── exports/                # Kibana saved objects exports (.ndjson/.json)
└── screenshots/            # annotated screenshots referenced in README
```
> Empty folders include a `.gitkeep` so they persist in Git operations.

## Getting Started
1. Clone this repo
   ```bash
   git clone https://github.com/<your-username>/<repo>.git
   cd <repo>
   ```
2. (Optional) Import the sample dashboards into Kibana
   - **Kibana** → **Stack Management** → **Saved Objects** → **Import**
   - Select files from `exports/` (e.g., `dashboard.ndjson`).
   - Review any index pattern conflicts and complete the import.
3. Open the dashboards and adjust the time range to match your dataset.

## Screenshots
> Replace these with your actual files in `screenshots/` and keep names descriptive.
- Dashboard overview  
  ![Dashboard Overview](screenshots/dashboard_overview.png)
- Suspicious domains table  
  ![Suspicious Domains](screenshots/suspicious_domains_table.png)
- Weird URI proportion visualization  
  ![Weird URI Proportions](screenshots/weird_uri_proportion.png)

## Methodology Notes
- Time-bucketed counts for malware families using KQL/Lucene filters.
- Domain-centric tables joined with source IP via visual builder/lens.
- URI path analysis focusing on randomness, hostnames, and odd file extensions.
- Proportion charts to surface skewed patterns quickly.

## Redaction Notice
Screenshots may contain internal IPs, usernames, or hostnames. Redact sensitive data before publishing. If this came from a school or employer environment, scrub names and credentials.

## License
MIT — see [LICENSE](LICENSE) for details.