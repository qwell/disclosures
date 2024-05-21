# Maricopa County Superior Court eFiling

## Description

Insufficient permission check vulnerabilities allowed unauthorized users to access restricted documents through the Maricopa Superior Court eFiling system's API endpoint. These issues were due to the ability to manipulate user IDs in API requests, potentially exposing sensitive information from recent court filings.

## Details

The vulnerabilities were discovered on the Maricopa County Superior Court [eFiling platform](https://efiling.clerkofcourt.maricopa.gov/Web/). The key issue lay in an API endpoint accessed when visiting the "My Filings" page. This endpoint, when provided with a numeric user ID, returned all filings submitted by that user in the last seven days. The response included document IDs and URLs for the documents associated with the filing.

An attacker could exploit this vulnerability by sending the numeric user ID of another user to the API endpoint. Due to the wide but manageable range of sequential user IDs (estimated to be around 90,000), it was feasible for an attacker to scan and find recent document submissions. This manipulation would have allowed unauthorized access to restricted documents.

For example, a particularly sensitive document could be accessed via a URL similar to `/Adlib/Output/20240419/202404157346581_PSYCH_EVAL_DOE_JOHN.pdf`, demonstrating the severity of the potential breach.

## Timeline

- 2024-04-25 - Vulnerability discovered in eFiling platform.
- 2024-04-25 - Maricopa County notified that vulnerabilities exist in eFiling platform.
- 2024-04-27 - Vulnerability details reported to Maricopa County.
- 2024-04-27 - Maricopa County confirms receipt of report[^1].
- 2024-04-28 - Maricopa County fixes vulnerability.
- 2024-05-16 - Vulnerabilities confirmed fixed.

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

[^1]: _Maricopa County's response should be applauded. They quickly shut down the site and began vulnerability scans (the results of which are unknown)._
