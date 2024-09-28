# Georgia Voter Registration Cancellation Portal

## Description

A critical vulnerability was discovered in Georgia’s voter registration cancellation portal, allowing unauthorized individuals to submit a cancellation request without proper identity verification. The issue involved bypassing the driver's license or Social Security number requirement, leaving the registration of any voter susceptible to exploitation.

## Details

The flaw in the Georgia voter registration cancellation portal permitted the submission of cancellation requests using only publicly available information, such as a voter's name, date of birth, and county of residence. These details, which can be easily obtained through public records or online searches, were sufficient to pass the initial validation screen. However, the portal required a driver's license number or the last four digits of a Social Security number to complete the process. By accessing the website's HTML code and removing the lines that enforced this validation step, it became possible to bypass the requirement entirely. Upon doing so, the system accepted the submission and displayed a success message, confirming that the cancellation request had been processed.

This vulnerability posed a significant risk due to the ease with which such public information could be accessed. In many cases, voters’ names, birthdates, and counties of residence are available through online resources, making the exploitation of this flaw relatively simple. Once a cancellation request was submitted, county election officials would have been tasked with processing the application, potentially canceling legitimate voter registrations without the individual's knowledge.

Though the system relied on manual oversight at the county level to reject incomplete applications lacking critical identification information, the portal itself lacked automated safeguards to prevent the submission of such requests. The system did not alert users to the missing information, instead allowing the flawed submission to proceed through its processes.

Upon discovery of the vulnerability, steps were taken to patch the portal and prevent further exploitation. The update ensured that any submission missing required identifying information, such as a driver's license number or Social Security digits, would trigger an error message and prevent the request from being processed. This correction aimed to close the loophole that previously allowed incomplete submissions to bypass verification.

**CVSS Score:** 8.6 (CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:N/I:H/A:N)

## Timeline

- 2024-08-05 - Vulnerability reported to Georgia Secretary of State.
- 2024-08-05 - Vulnerability confirmed fixed.

## Contact

[Jason Parker](https://linktr.ee/northantara)

- Email: [north@ꩰ.com](mailto:north@ꩰ.com)
- Press: [press@jeltz.org](mailto:press@jeltz.org)
- Mastodon: [@north@ꩰ.com](https://ꩰ.com/@north)

## Support

- If you enjoy my work, consider becoming a sponsor on [Patreon](https://patreon.com/northantara) or [GitHub](https://github.com/sponsors/qwell/), and/or consider donating to the [Electronic Frontier Foundation](https://eff.org/donate) or [St. Jude](https://www.stjude.org/donate). Many hours of labor are put into researching and disclosing vulnerabilities.

## Other Disclosures

- [govtech.cc](https://govtech.cc/)
