Security and Compliance | FinFeedAPI.com Documentation




[Skip to main content](#__docusaurus_skipToContent_fallback)

[![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)![FinFeedAPI.com](https://cdn.sanity.io/images/xpx4czto/production/875913d8710b3054c19fad19673dc5592614265e-773x184.svg)](https://www.finfeedapi.com)[Stock API](/stock-api/)[SEC API](/sec-api/)[Currencies API](/currencies-api/)[Platform Documentation](/general/authentication)

[GitHub](https://github.com/api-bricks/api-bricks-sdk)[Status Page](https://status.finfeedapi.com)

Search

[Get a free API Key](https://console.finfeedapi.com/?link=/apikeys/create)

* [Authentication](/general/authentication)
* [Security and Compliance](/general/security)
* [Throttling](/general/throttling)
* [Usage Credits](/general/usage-credits)
* [Customer Portal](/general/customer-portal/)
* [MCP Servers](/general/mcp-servers)
* [Product Changelog](/general/changelog/)
* [Product Roadmap](/general/roadmap)

* Security and Compliance

On this page

Security and Compliance
=======================

FinFeedAPI prioritizes the security and compliance of its platform, implementing robust measures to protect user data and ensure seamless integration with various environments. This article provides an overview of our security mechanisms, access controls, and compliance standards.

Application Layer Protection[​](/general/security#application-layer-protection "Direct link to Application Layer Protection")
-----------------------------------------------------------------------------------------------------------------------------

FinFeedAPI employs multiple security mechanisms to protect the application layer exposed to the internet:

* **TLS Encryption**: All communications are encrypted using TLS 1.2 (AES-256) or higher, ensuring data confidentiality during transmission and preventing man-in-the-middle attacks.
* **API Key Authentication**: A fundamental method for authenticating and controlling access to FinFeedAPI services.
* **JWT Token Authentication**: An extended security measure combining API keys with JWT tokens for enhanced protection.
* **TLS Client Certificates**: Used for authenticating FIX sessions and Managed Cloud REST API access.

Rationale: These layered security measures provide robust protection against unauthorized access, data interception, and man-in-the-middle attacks. TLS encryption, in particular, ensures that data transmitted between the client and server remains confidential and tamper-proof, making it extremely difficult for malicious actors to intercept or modify the communication.

Access Restriction Methods[​](/general/security#access-restriction-methods "Direct link to Access Restriction Methods")
-----------------------------------------------------------------------------------------------------------------------

FinFeedAPI supports various methods to restrict platform access by source IP for Enterprise plan customers:

1. **IP Whitelisting**: Configure your account to allow access only from specific IP addresses.
2. **Web Application Firewall (WAF)**: Filter and monitor HTTP requests based on IP addresses.
3. **Security Groups**: For cloud-hosted services, use security groups to restrict access to specific IP ranges.

Rationale: These methods provide flexible options for organizations to implement strict access controls based on their specific security requirements. By offering these features exclusively to Enterprise customers, FinFeedAPI ensures that high-security environments have access to advanced protection measures.

Note: Access restriction methods are currently available only for Enterprise plans. Please contact our sales team for more information on upgrading to an Enterprise plan to access these features.

Role-Based Access Control[​](/general/security#role-based-access-control "Direct link to Role-Based Access Control")
--------------------------------------------------------------------------------------------------------------------

FinFeedAPI implements role-based access control within the Customer Portal:

1. **Admin Role**:

   * Same capabilities as the account owner
   * Can add subscriptions, edit billing information, and manage users
   * Full access to Customer Portal administrative functions
2. **User Role**:

   * Can log in to the Customer Portal
   * View account usage and track metrics
   * Limited capabilities compared to Admins

Rationale: This role-based system ensures that users have appropriate access levels based on their responsibilities, adhering to the principle of least privilege.

Integration and Authentication[​](/general/security#integration-and-authentication "Direct link to Integration and Authentication")
-----------------------------------------------------------------------------------------------------------------------------------

For integration with external environments:

* **Principle of Least Privilege**: FinFeedAPI provides various authentication methods that do not require administrative privileges.
* **Mutual TLS (mTLS) Support**: Available for secure, authenticated communication between clients and servers. This feature is exclusive to Enterprise plan customers.

Rationale: These practices ensure secure integration while minimizing potential security risks associated with over-privileged access. The availability of mTLS for Enterprise customers provides an additional layer of security for organizations with stringent authentication requirements.

Note: Mutual TLS (mTLS) support is currently available only for Enterprise plans. If you require this feature, please contact our sales team for information on upgrading to an Enterprise plan.

Encryption and Key Management[​](/general/security#encryption-and-key-management "Direct link to Encryption and Key Management")
--------------------------------------------------------------------------------------------------------------------------------

FinFeedAPI utilizes robust encryption and key management practices:

* **Cryptographic Module**: Uses Google Cloud Platform (GCP) Cloud Key Management Service (KMS) for key management.
* **Secure Key Storage**: Encryption keys are not stored in clear text, and full keys are not accessible in the customer portal.

Rationale: These measures provide industry-standard protection for sensitive data and encryption keys.

User Credential Security[​](/general/security#user-credential-security "Direct link to User Credential Security")
-----------------------------------------------------------------------------------------------------------------

FinFeedAPI employs robust security measures for user authentication and credential protection:

* **Password Hashing**: We use Firebase Authentication, which implements an internally modified version of scrypt to hash account secrets. This provides strong protection against password cracking attempts.
* **Automatic Rehashing**: Even if an account is initially uploaded with a password using a different algorithm, Firebase Auth automatically rehashes the password using its secure method upon the first successful login.
* **Passwordless Options**: FinFeedAPI supports various authentication methods that don't require storing passwords, including:
  + Magic link authentication
  + Google authentication
  + GitHub authentication
* **Channel Encryption**: TLS 1.2 (AES-256) or higher is used for all data transmission and system console access.

Rationale: By leveraging Firebase Authentication's secure hashing methods and offering passwordless authentication options, FinFeedAPI significantly reduces the risk of password-related vulnerabilities. The automatic rehashing feature ensures that all passwords are protected using the most secure method available, even if they were initially set using a different algorithm. Additionally, the support for passwordless authentication methods further enhances security by eliminating the need to store passwords for users who choose these options.

Data Protection and Privacy[​](/general/security#data-protection-and-privacy "Direct link to Data Protection and Privacy")
--------------------------------------------------------------------------------------------------------------------------

FinFeedAPI implements additional measures to protect sensitive data:

* **Data Obfuscation and Masking**: Sensitive data accessed via our API is obfuscated and masked to prevent unauthorized exposure.
* **Secure Data Handling**: We employ industry-standard practices to ensure that sensitive information is protected throughout its lifecycle.

Rationale: By obfuscating and masking sensitive data, FinFeedAPI adds an extra layer of protection against potential data breaches or unauthorized access. This practice helps maintain user privacy and complies with data protection regulations.

Data Segregation and Audit Trails[​](/general/security#data-segregation-and-audit-trails "Direct link to Data Segregation and Audit Trails")
--------------------------------------------------------------------------------------------------------------------------------------------

* **Dedicated Infrastructure**: Available as part of the Enterprise solution or as an additional service.
* **Logical Segregation**: Implemented through unique identifiers and access controls.
* **Immutable Audit Trails**: FinFeedAPI does not allow modifications to audit trails.
* **Audit Trail Access**: Can be made available within 7 business days and exposed via API for integration with external systems.

Rationale: These features ensure data isolation between customers and maintain the integrity of audit logs for compliance and security purposes.

Conclusion[​](/general/security#conclusion "Direct link to Conclusion")
-----------------------------------------------------------------------

FinFeedAPI's comprehensive security and compliance measures demonstrate our commitment to protecting user data and supporting seamless integration with various enterprise environments. By implementing industry-standard security practices and offering flexible configuration options, FinFeedAPI provides a secure and reliable platform for financial data feed services.

Was this section helpful?

* 1
* 2
* 3
* 4
* 5

[Previous

Authentication](/general/authentication)[Next

Throttling](/general/throttling)

* [Application Layer Protection](/general/security#application-layer-protection)
* [Access Restriction Methods](/general/security#access-restriction-methods)
* [Role-Based Access Control](/general/security#role-based-access-control)
* [Integration and Authentication](/general/security#integration-and-authentication)
* [Encryption and Key Management](/general/security#encryption-and-key-management)
* [User Credential Security](/general/security#user-credential-security)
* [Data Protection and Privacy](/general/security#data-protection-and-privacy)
* [Data Segregation and Audit Trails](/general/security#data-segregation-and-audit-trails)
* [Conclusion](/general/security#conclusion)

Copyright © 2025 API BRICKS LTD or its affiliates. All rights reserved.