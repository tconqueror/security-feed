# MongoDB warns admins to patch severe RCE flaw immediately

![MongoDB](https://www.bleepstatic.com/content/hl-images/2025/12/23/mongoDB.jpg)

MongoDB has warned IT admins to immediately patch a high-severity vulnerability that can be exploited in remote code execution (RCE) attacks targeting vulnerable servers.

Tracked as [CVE-2025-14847](https://nvd.nist.gov/vuln/detail/CVE-2025-14847), this security flaw affects multiple MongoDB and MongoDB Server versions and can be exploited by unauthenticated threat actors in low-complexity attacks that don't require user interaction.

CVE-2025-14847 is due to an [improper handling of length parameter inconsistency](https://cwe.mitre.org/data/definitions/130.html), which can allow attackers to execute arbitrary code and potentially gain control of targeted devices.

[![Wiz](https://www.bleepstatic.com/c/a/as-Free-Phishing-970x250.jpg)](https://www.adaptivesecurity.com/lp/nb/free-phishing-test?utm%5Fsource=display%5Fnetwork&utm%5Fmedium=paid%5Fdisplay&utm%5Fcampaign=2025%5F12%5FLinkedin%5FSocial%5FNA%5FBrand%5FAwareness%5FTeachers%5Ffunding&utm%5Fid=701Rd00000ZoWjjIAF%2F&utm%5Fcontent=970%5F250) 

To patch the security flaw and block potential attacks, admins are advised to immediately upgrade to MongoDB 8.2.3, 8.0.17, 7.0.28, 6.0.27, 5.0.32, or 4.4.30.

The vulnerability impacts the following MongoDB versions:

* MongoDB 8.2.0 through 8.2.3
* MongoDB 8.0.0 through 8.0.16
* MongoDB 7.0.0 through 7.0.26
* MongoDB 6.0.0 through 6.0.26
* MongoDB 5.0.0 through 5.0.31
* MongoDB 4.4.0 through 4.4.29
* All MongoDB Server v4.2 versions
* All MongoDB Server v4.0 versions
* All MongoDB Server v3.6 versions

"An client-side exploit of the Server's zlib implementation can return uninitialized heap memory without authenticating to the server. We strongly recommend upgrading to a fixed version as soon as possible," MongoDB's security team [said in a Friday advisory](https://jira.mongodb.org/browse/SERVER-115508).

"We strongly suggest you upgrade immediately. If you cannot upgrade immediately, disable zlib compression on the MongoDB Server by starting mongod or mongos with a networkMessageCompressors or a net.compression.compressors option that explicitly omits zlib."

The U.S. Cybersecurity and Infrastructure Security Agency (CISA) added [another MongoDB RCE flaw](https://www.cisa.gov/news-events/alerts/2021/12/10/cisa-adds-13-known-exploited-vulnerabilities-catalog) (CVE-2019-10758) to its catalog of known exploited vulnerabilities four years ago, tagging it as actively exploited and ordering federal agencies to secure their systems, as mandated by [Binding Operational Directive (BOD) 22-01](https://www.cisa.gov/binding-operational-directive-22-01).

MongoDB is a popular non-relational database management system (DBMS) that, unlike relational databases such as PostgreSQL and MySQL, stores data in BSON (Binary JSON) documents instead of tables.

The database software is used by more than 62,500 customers worldwide, including dozens of Fortune 500 companies.