# Disclosures

## Timeline

### [NYPD Officer Complaints / RockDaisy Athlete Management System](https://govtech.cc/README-2024-05-17-rockdaisy.md)

**2024-05-17**

Insufficient permission check vulnerabilities in NYPD's officer complaints platform, RockDaisy Athlete Management System, allowed unauthenticated attackers to access the administrative dashboard. Attackers could view and edit user accounts, SQL queries, database connection information, and officer profile data. Additionally, it was possible to add malicious files (such as PDFs or executables) to the Azure datastore and serve them to users who requested officer complaints.

### [Maricopa County Superior Court eFiling](https://govtech.cc/README-2024-05-17-maricopa.md)

**2024-05-17**

Insufficient permission check vulnerabilities allowed unauthorized users to access restricted documents through the Maricopa Superior Court eFiling system's API endpoint. These issues were due to the ability to manipulate user IDs in API requests, potentially exposing sensitive information from recent court filings.

### [Catalis EZ-Filing v4](https://govtech.cc/README-2024-05-04-catalis-ez-filing-v4.md)

**2024-05-04**

An insufficient permission check vulnerability in [Catalis](https://catalisgov.com/)'s EZ-Filing v4 eFiling platform allowed authenticated attackers to extract personal data, such as names, addresses, emails, and phone numbers, from user accounts by manipulating POST requests. This security flaw exposes users to potential identity theft and fraud.

EZ-Filing v4 is used by [Georgia](https://ez-filing.net/georgia) and [South Carolina](https://ez-filing.net/southcarolina).

### [Catalis EZ-Filing v3](https://govtech.cc/README-2024-05-04-catalis-ez-filing-v3.md)

**2024-05-04**

An insufficient permission check vulnerability in [Catalis](https://catalisgov.com/)'s EZ-Filing v3 eFiling platform allowed authenticated users to access sealed documents, such as mental health reports in guardianship cases, exposing highly sensitive and confidential information. This security flaw compromises the privacy and safety of vulnerable individuals involved in legal proceedings.

EZ-Filing v3 is used by [Maine](https://maineprobate.net/efiling).

### [Granicus GovQA](https://govtech.cc/README-2024-03-07-granicus-govqa.md)

**2024-03-06**

Insufficient permission check vulnerabilities in [Granicus](https://granicus.com/)'s GovQA allowed unauthorized access to view, edit, and change ownership of open records requests, including restricted-access confidential records. By changing ownership of a request, an attacker could effectively deny a legitimate user's access to that request. The vulnerabilities affected various deployments, including numerous Departments of Children and Family Services or their equivalents, which handle highly sensitive records of domestic violence and sexual abuse allegations against children.

### [Granicus eFiling](#granicus-efiling)

**2024-03-02**

Vulnerabilities in [Granicus](https://granicus.com/)'s eFiling platform allowed attackers to register accounts in any organization of their choosing, including the organization that granted administrator privileges. Administrators have carte blanche access to all filings in all cases. Additionally, an organization owner could force any user into their own organization, which allowed the organization owner to effectively revoke privileges of administrators or other organization owners.

Granicus's eFiling platform is used statewide in [Florida](https://www.myflcourtaccess.com/default.aspx) and [Arizona](https://efile.azcourts.gov/).

Administrator accounts could be registered by sending a POST to `/api/Security/RegisterUser` with the following JSON.

```JSON
{
  "User":{
    "OrganizationId":"0","IsAdministrator":true,"UserTypeCode":"10",
    "IdType":-1,"IdTypeSpecified":false,"IdState":"-1","IdNumber":"",
    "LogonName":"<username>","LogonPassword":"<password>",
    "FirstName":"Example","MiddleName":"","LastName":"User","Suffix":"",
    "PrimaryEmailAddress":"fake@example.com","AlternateEmailAddress1":"","AlternateEmailAddress2":"",
    "Address1":"123 Fake St","Address2":"","City":"Beverly Hills","State":"CA","ZipCode":"90210",
    "Country":"US","CountryCode":"US","PhoneNumber":"","PhoneExtension":""
  },"ForceToPendingApproval":false,"ForceCreateUser":false
}
```

_Note: Shortly after receiving my report, Granicus evidently leaked my information to the Arizona Supreme Court. For the next two months, Granicus and the Arizona Supreme Court cyberstalked me; my LinkedIn profile was viewed repeatedly, sometimes multiple times per day, by several employees from each company._

### [Disorder in the Court](https://govtech.cc/README-2023-11-30-disorder-in-the-court.md)

**2023-11-30**

Insufficient permission check vulnerabilities in public court record platforms from multiple vendors allowed unauthorized public access to sealed, confidential, unredacted, and/or otherwise restricted case documents. Affected documents include witness lists and testimony, mental health evaluations, child custody agreements, detailed allegations of abuse, corporate trade secrets, jury forms, and much more.

- [All Vendors (Combined)](https://govtech.cc/README-2023-11-30-disorder-in-the-court.md)
- [Catalis -- CMS360](https://github.com/qwell/disorder-in-the-court/blob/main/README-Catalis.md)
- [Henschen & Associates -- CaseLook](https://github.com/qwell/disorder-in-the-court/blob/main/README-Henschen%26Associates.md)
- [Tyler Technologies -- Court Case Management Plus](https://github.com/qwell/disorder-in-the-court/blob/main/README-TylerTechnologies.md)
- [Florida](https://github.com/qwell/disorder-in-the-court/blob/main/README-Florida.md)
  - Brevard County
  - Hillsborough County
  - Lee County
  - Monroe County
  - Sarasota County

### [BluHorse Inmate Management](https://ꩰ.com/@north/111365131136729011)

**2023-11-06**

- Leaked personal data of inmates and officers.

### [Bluesky Social Network](https://github.com/qwell/bsky-exploits)

**2023-09-13**

- Abitrary text descriptions and thumbnails in link cards.
- Disguised links in post text.

## Contact

[Jason Parker](https://linktr.ee/northantara)

- Email: [north@ꩰ.com](mailto:north@ꩰ.com)
- Press: [press@jeltz.org](mailto:press@jeltz.org)
- Mastodon: [@north@ꩰ.com](https://ꩰ.com/@north)

## Support

- If you enjoy my work, consider becoming a sponsor on [Patreon](https://patreon.com/northantara) or [GitHub](https://github.com/sponsors/qwell/), and/or consider donating to the [Electronic Frontier Foundation](https://eff.org/donate) or [St. Jude](https://www.stjude.org/donate). Many hours of labor are put into researching and disclosing vulnerabilities.
- I am also available for both contractual and full-time employment opportunities.
