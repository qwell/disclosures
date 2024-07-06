# NYPD Officer Complaints / RockDaisy Athlete Management System

## Description

Insufficient permission check vulnerabilities in NYPD's [officer complaints](https://nypdonline.org/link/2) platform, [RockDaisy](https://rockdaisy.com) Athlete Management System[^1], allowed unauthenticated attackers to access the administrative dashboard. Attackers could view and edit user accounts, SQL queries, database connection information, and officer profile data. Additionally, it was possible to add malicious files (such as PDFs or executables) to the Azure datastore and serve them to users who requested officer complaints.

## Details

By modifying several JavaScript variables, attackers could bypass client-side access restrictions. Once the administrative dashboard was loaded, attackers had nearly full control over site settings including the Azure datastore connection string that provides full access to the unprotected datastore.

Specifically, an attacker would set the following variables when particular JavaScript debugger breakpoints were reached:

- `e.disallowNotAdministrators = false`
- `e.loginLink = true` (and later, `e.loginLink = false`)
- `r.defaultPrevented = false`
- `u.clientConfig.IsSignInDisabled = false`

CVSS 10.0 (CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:N/VC:H/VI:H/VA:H/SC:H/SI:H/SA:H)

## Timeline

- 2024-05-10 - Vulnerability discovered in NYPD Officer Complaints site.
- 2024-05-10 - Vulnerability details reported to New York City.
- 2024-05-11 - Vulnerability details reported to RockDaisy.
- 2024-05-11 - New York City confirms receipt of report.
- 2024-05-13 - Vulnerability details reported to NYPD.
- 2024-05-13 - NYPD confirms receipt of report.
- 2024-05-14 - Vulnerabilities confirmed mitigated by NYC/NYPD.
- 2024-05-15 - Follow-up #1 sent to RockDaisy.
- 2024-05-16 - Follow-up #2 sent to RockDaisy.

## Contact

[Jason Parker](https://linktr.ee/northantara)

- Email: [north@ꩰ.com](mailto:north@ꩰ.com)
- Press: [press@jeltz.org](mailto:press@jeltz.org)
- Mastodon: [@north@ꩰ.com](https://ꩰ.com/@north)

## Support

- If you enjoy my work, consider becoming a sponsor on [Patreon](https://patreon.com/northantara) or [GitHub](https://github.com/sponsors/qwell/), and/or consider donating to the [Electronic Frontier Foundation](https://eff.org/donate) or [St. Jude](https://www.stjude.org/donate). Many hours of labor are put into researching and disclosing vulnerabilities.
- I am also available for both contractual and full-time employment opportunities.

## Other Disclosures

- [govtech.cc](https://govtech.cc/)

[^1]: _wat?_
