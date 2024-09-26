# Multiple Vulnerabilities in GovQA

## Description

Several critical vulnerabilities were identified in GovQA, a platform used by government agencies for case and document management. These vulnerabilities included the leakage of usernames and emails, the ability to reset passwords without answering security questions, and the capability to reset any password without knowing the username.

## Details

Username/Email Leak

- Attackers could manipulate the `cid` parameter in the URL (e.g. `https://hillsboroughsheriff.govqa.us/WEBAPP/_rs/AnonymousCustomerResetPassword.aspx?sSessionID=&cid=64529`) to access and retrieve usernames and email addresses of other users. By changing the `cid` value to different numbers, they were able to obtain information about various users without authorization.

Password Reset Without Security Questions

- Certain user accounts could have had their passwords reset by accessing the password reset confirmation page (e.g. `https://hillsboroughsheriff.govqa.us/WEBAPP/_rs/AnonymousCustomerConfirmPassword.aspx?sSessionID=&cid=64529`) without requiring the answer to any predefined security questions. This allowed unauthorized individuals to reset passwords and gain access to those accounts without any form of verification.

Password Reset Without Username

- Attackers were able to reset any user's password without knowing their username or providing any security answers.

**CVSS Score:** 9.8 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H)

## Timeline

- **2024-08-05:** Vulnerabilities reported to Granicus via email.
- **2024-08-05:** Granicus acknowledged receipt of the report.
- **2024-08-09:** Granicus confirmed that all reported vulnerabilities were resolved and deployed to production.
- **2024-08-12:** Follow-up communication to confirm all vulnerabilities were fixed.
- **2024-08-14:** Confirmation from Granicus that all confirmed vulnerabilities have been mitigated.

## Contact

[Jason Parker](https://linktr.ee/northantara)

- Email: [north@ꩰ.com](mailto:north@ꩰ.com)
- Press: [press@jeltz.org](mailto:press@jeltz.org)
- Mastodon: [@north@ꩰ.com](https://ꩰ.com/@north)

## Support

- If you enjoy my work, consider becoming a sponsor on [Patreon](https://patreon.com/northantara) or [GitHub](https://github.com/sponsors/qwell/), and/or consider donating to the [Electronic Frontier Foundation](https://eff.org/donate) or [St. Jude](https://www.stjude.org/donate). Many hours of labor are put into researching and disclosing vulnerabilities.

## Other Disclosures

- [govtech.cc](https://govtech.cc/)
