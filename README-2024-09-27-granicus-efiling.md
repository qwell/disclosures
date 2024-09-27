# Multiple Vulnerabilities in Granicus eFiling Platform

## Description

Several critical vulnerabilities were identified in Granicus's eFiling platforms. These vulnerabilities included the leakage of sensitive user information, the ability to modify user accounts without proper authorization, the potential to deny users access by duplicating usernames, and privilege escalation through manipulation of organization type codes.

## Details

### Sites

- [https://efile.azcourts.gov/](https://efile.azcourts.gov/)
- [https://www.myflcourtaccess.com/](https://www.myflcourtaccess.com/)

### 1. Username/Email Leak

Attackers could obtain names, email addresses, and phone numbers for every user by interacting with various API endpoints. By sending specific POST requests with manipulated parameters, sensitive user information was exposed.

- **Example API Endpoint:**
  - `POST /api/Security/SearchFilers` with payload `{ "IncludeJudges": true, "LastName": "%%%" }`
  - `POST /api/Security/GetManagedUsers` to retrieve users with organizations.
  - `POST /api/Security/GetUnaffiliatedUsers` to retrieve users without organizations.

### 2. Modify User Account Information

Certain user accounts could have their information, including passwords, modified without additional controls. This vulnerability was present for users not associated with any organization. Unauthorized individuals could alter account details without notifications or required acceptance.

- **Example API Endpoint:**
  - `POST /api/security/AssociateUsersToCurrentUsersOrganization` with payload `{ "UserIds": ["34"] }`

### 3. Deny Users the Ability to Log In

Attackers could prevent users from logging in by creating or updating accounts with duplicate usernames. This was achievable by manipulating the username during user creation or via the User Details page, leading to login failures for the original user.

- **Example API Endpoints:**
  - `POST /api/security/RegisterUser` with duplicate username.
  - `POST /api/security/UpdateUser` to change username to an existing one.

### 4. Privilege Escalation

By registering an organization with a TypeCode matching that of higher-privileged organizations (e.g., courts or Granicus administrators), attackers could escalate their privileges within the platform. This allowed users within such organizations to inherit elevated access levels.

- **Example API Endpoint:**

  - `POST /api/security/RegisterOrganization` with payload `{ "Organization": { "TypeCode": 3, "Name": "...etc" }, "User": { "UserTypeCode": 10, "LogonName": "...etc" } }`

**CVSS Score:** 9.8 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H)

## Timeline

- 2024-03-31 - Vulnerabilities reported to Granicus via email.
- 2024-04-01 - Granicus acknowledged receipt of the report.
- 2024-06-13 - Follow-up communication to confirm remediation.
- 2024-07-07 - Further follow-up due to lack of updates; expressed frustration with Granicus's handling.
- 2024-07-08 - Granicus stated the issues were resolved at the end of April.
- 2024-07-09 - Final follow-up to note that future reports would be handled on a much more aggressive timeline.[^1]

## Contact

[Jason Parker](https://linktr.ee/northantara)

- Email: [north@ꩰ.com](mailto:north@ꩰ.com)
- Press: [press@jeltz.org](mailto:press@jeltz.org)
- Mastodon: [@north@ꩰ.com](https://ꩰ.com/@north)

## Support

- If you enjoy my work, consider becoming a sponsor on [Patreon](https://patreon.com/northantara) or [GitHub](https://github.com/sponsors/qwell/), and/or consider donating to the [Electronic Frontier Foundation](https://eff.org/donate) or [St. Jude](https://www.stjude.org/donate). Many hours of labor are put into researching and disclosing vulnerabilities.

## Other Disclosures

- [govtech.cc](https://govtech.cc/)

[^1]: Granicus handled these vulnerabilities with significant delays and inadequate communication, demonstrating a lack of responsiveness and proper security practices. Due to this, Granicus was given notice that future reports would allow 2 days to provide ETAs and 7 days to provide remediation.
