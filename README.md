# Disclosures

## Timeline

### [VendorC eFiling](#vendorc-efiling)

**2024-04-??**

An insufficient permission check vulnerability in VendorC's court eFiling platform allows an attacker to view eFiling submissions (and their associated documents, regardless of confidentiality) filed by other users.

- Reported: 2024-03-30

### [VendorB eFiling](#vendorb-efiling)

**2024-04-??**

Multiple vulnerabilities in VendorB's court eFiling platform allow an attacker to obtain the name, email, and phone number associated with every account; modify details of user accounts, including password and other sensitive information; deny access to user accounts; and gain administrator privileges.

- Reported: 2024-03-30

### [VendorA eFiling](#vendora-efiling)

**2024-04-??**

Multiple vulnerabilities in VendorA's court eFiling platform allow an attacker to obtain private information from any user account and view eFiling submissions (and their associated documents, regardless of confidentiality) filed by other users.

- Reported: 2024-03-30

### [Granicus GovQA](https://github.com/qwell/disclosure-granicus-govqa)

**2024-03-06**

Insufficient permission check vulnerabilities in Granicus's GovQA allowed unauthorized access to view, edit, and change ownership of open records requests, including restricted-access confidential records. By changing ownership of a request, an attacker could effectively deny a legitimate user's access to that request. The vulnerabilities affected various deployments, including numerous Departments of Children and Family Services or their equivalents, which handle highly sensitive records of domestic violence and sexual abuse allegations against children.

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

### [Disorder in the Court](https://github.com/qwell/disorder-in-the-court)

**2023-11-30**

Insufficient permission check vulnerabilities in public court record platforms from multiple vendors allowed unauthorized public access to sealed, confidential, unredacted, and/or otherwise restricted case documents. Affected documents include witness lists and testimony, mental health evaluations, child custody agreements, detailed allegations of abuse, corporate trade secrets, jury forms, and much more.

- [All Vendors (Combined)](https://github.com/qwell/disorder-in-the-court/blob/main/README.md)
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

## Sponsorship

- If you enjoy my work, consider becoming a sponsor on [Patreon](https://patreon.com/northantara) or [GitHub](https://github.com/sponsors/qwell/), and/or consider donating to the [Electronic Frontier Foundation](https://eff.org/donate) or [St. Jude](https://www.stjude.org/donate). Many hours of unpaid labor are put into researching and disclosing vulnerabilities.
