# EZ-Filing v4

## Description

An insufficient permission check vulnerability in [Catalis](https://catalisgov.com/)'s EZ-Filing v4 eFiling platform allowed authenticated attackers to extract personal data, such as names, addresses, emails, and phone numbers, from user accounts by manipulating POST requests. This security flaw exposes users to potential identity theft and fraud.

EZ-Filing v4 is used by [Georgia](https://ez-filing.net/georgia) and [South Carolina](https://ez-filing.net/southcarolina).

## Details

- **Method A:** Navigating to the New Case Wizard section (`https://ez-filing.net/georgia/NewCaseWizard.aspx`) and using `PageMethods.GetAccountInfo(12244);` to retrieve information.
- **Method B:** Sending a direct POST request to `https://ez-filing.net/georgia/NewCaseWizard.aspx/GetAccountInfo` with JSON payload `{ "accountID": 12244 }`, applicable to multiple state directories like /georgia/ and /southcarolina/.

## Timeline

- 2024-03-24 - Vulnerability discovered in EZ-Filing v4.
- 2024-03-30 - Vulnerability details reported to Catalis.
- 2024-04-09 - Follow-up #1 sent to Catalis.
- 2024-04-19 - Follow-up #2 sent to Catalis.
- 2024-04-23 - Vulnerability report escalated to PSG Equity[^1].
- 2024-04-23 - PSG Equity CISO confirms receipt of report and contacts Catalis management.
- 2024-04-30 - PSG Equity CISO says that the vulnerability has been fixed.
- 2024-04-30 - Vulnerabilities confirmed fixed.

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

[^1]: _Catalis CEO Scott Roza previously requested that I email him reports directly; no response was provided. The issue was escalated to PSG Equity's CISO. PSG Equity is a majority stakeholder of Catalis._
