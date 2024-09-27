# Thomson Reuters C-Track eFiling Privilege Escalation Vulnerability

## Description

An insufficient permission check vulnerability in Thomson Reuters's C-Track eFiling system allowed users to assign themselves privileged roles, such as `Clerk`, during the registration process. By manipulating form data, attackers could gain unauthorized access to administrative functionalities and sensitive court data.

## Details

During the user registration process, the platform provides a dropdown menu for role selection. However, the system fails to enforce proper server-side validation on the selected role. By modifying the `applicationRoleId` parameter in the form data, an attacker can assign themselves any role, including privileged roles like `Clerk` (role ID `90000`).

Specifically, an attacker would:

- Begin the registration process as a new eFile user via the Okta login page (e.g., `https://mtefile.courts.mt.gov/saml/login`).
- When reaching the registration page (`https://mtefile.courts.mt.gov/register/new`), change the `applicationRoleId` in the role selection dropdown to a privileged role ID, such as `90000` for `Clerk`.
- Fill out the remaining form fields and submit the registration.

Upon completion, the newly created account will possess the privileges associated with the clerk role, granting access to sensitive areas and functionalities of the eFiling system.

**Impact:**

An attacker with clerk-level access could:

- View, modify, or delete sensitive court documents.
- Alter case information or court schedules.
- Disrupt judicial proceedings by manipulating official records.

**CVSS Score:** 9.1 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:N)

## Timeline

- 2024-06-03 - Vulnerability discovered and reported to Thomson Reuters via HackerOne.
- 2024-06-04 - Vulnerability triaged and acknowledged by HackerOne analyst.
- 2024-07-07 - Followed up due to lack of communication.
- 2024-08-14 - Followed up again after no response.
- 2024-09-06 - Followed up again after no response. Intent to disclose communicated.
- 2024-09-24 - Thomson Reuters reported a fix had been released.
- 2024-09-25 - Vulnerability confirmed fixed.

## Contact

[Jason Parker](https://linktr.ee/northantara)

- Email: [north@ꩰ.com](mailto:north@ꩰ.com)
- Press: [press@jeltz.org](mailto:press@jeltz.org)
- Mastodon: [@north@ꩰ.com](https://ꩰ.com/@north)

## Support

- If you enjoy my work, consider becoming a sponsor on [Patreon](https://patreon.com/northantara) or [GitHub](https://github.com/sponsors/qwell/), and/or consider donating to the [Electronic Frontier Foundation](https://eff.org/donate) or [St. Jude](https://www.stjude.org/donate). Many hours of labor are put into researching and disclosing vulnerabilities.

## Other Disclosures

- [govtech.cc](https://govtech.cc/)
