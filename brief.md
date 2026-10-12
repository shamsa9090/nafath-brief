Version: NAFATH-V1
Track: Networking

## Overview
A secure national digital login service allows citizens to access multiple government services using one account through a website or mobile application. Software development provides the login system and connects government applications through secure identity protocols. Artificial intelligence can help identify unusual login activities, while human oversight reduces the risk of incorrect decisions. Mobile security controls application permissions and protects access to sensitive device features. Networking technologies support reliable communication and improve the privacy of network requests. Cybersecurity protects user accounts through strong authentication methods and safeguards against phishing attacks. Data protection ensures that citizens' personal information is collected, stored, and processed according to applicable laws.Together, these six fields support a trustworthy national login service, with Networking focusing on how DNS over HTTPS (DoH) protects DNS queries and where its security limitations remain.

## Software
OAuth 2.0 is an authorization framework that allows applications to access protected resources with limited permissions. OpenID Connect (OIDC) adds an identity layer to OAuth 2.0 and supports user authentication. For the national digital login service, OIDC enables citizens to sign in and allows government applications to verify their identity using ID tokens. OAuth 2.0 supports delegated access to protected APIs through access tokens. These technologies serve different purposes and can work together in a secure single sign-on system.

Resource: OpenID Connect Core 1.0 - https://openid.net/specs/openid-connect-core-1_0.html
## AI
According to the NIST AI Risk Management Framework, the authority must manage reliability, security, privacy, transparency, accountability, and harmful bias before deploying AI-based login monitoring. The model could incorrectly flag legitimate citizens or miss suspicious activity. Its performance should be tested using representative data and monitored after deployment. Sensitive login information must be protected against unauthorized access. The authority should document decisions, explain how alerts are handled, and provide human oversight for high-impact decisions. These measures support responsible and trustworthy AI use.

Resource: NIST AI Risks and Trustworthiness - https://airc.nist.gov/airmf-resources/airmf/3-sec-characteristics/
## Mobile
Android's runtime permission model restricts access to sensitive device features, such as the camera, microphone, and location. Applications must request dangerous permissions while running, rather than receiving them automatically during installation. The national login application should request a permission only when the citizen uses a feature that requires it, such as scanning an identity document with the camera. Before accessing that feature, the app should check whether permission has been granted. If the user denies access, the application should handle the refusal gracefully and provide alternatives where possible.

Resource: Android Developers - Request runtime permissions - https://developer.android.com/training/permissions/requesting
## Networking
DNS over HTTPS (DoH) sends DNS queries and responses through encrypted HTTPS connections. According to RFC 8484, it protects DNS traffic against passive monitoring and certain attempts to redirect queries to malicious servers. However, DoH does not hide all browsing activity or prevent the DNS resolver from seeing requests. It also does not guarantee that DNS answers are authentic; DNSSEC addresses a different security problem. For a national login service, DoH improves DNS transport privacy but cannot replace other security controls.

Resource: RFC 8484 - DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/rfc/rfc8484.html
## Cybersecurity
Phishing-resistant authentication prevents attackers from reusing authentication responses on fraudulent websites. NIST recognizes cryptographic methods that bind authentication to the legitimate verifier, including FIDO2/WebAuthn passkeys and security keys. Client-authenticated TLS can also provide phishing resistance. In contrast, SMS codes, email codes, and manually entered one-time passwords are not phishing-resistant because attackers may relay them during a phishing attack. A national login service should prefer phishing-resistant multi-factor authentication, such as a passkey protected by a device PIN or biometric verification.

Resource: NIST SP 800-63B - Authenticators - https://pages.nist.gov/800-63-4/sp800-63b/authenticators/
## Data
Oman's Personal Data Protection Law, issued by Royal Decree 6/2022, requires controllers to establish safeguards and procedures for processing personal data. These include assessing risks, protecting confidentiality, and securing data transfers. Controllers must respect individuals' rights, maintain processing records, and notify the relevant authority and affected individuals of qualifying data breaches under applicable procedures. The law also addresses the appointment of a data protection officer and restrictions on disclosure. A national login service must apply these obligations when handling citizens' identity information.

Resource: Royal Decree 6/2022 - Personal Data Protection Law - https://decree.om/2022/l20220006/
## Misconception in My Track
A common misconception in networking is that DNS over HTTPS (DoH) makes DNSSEC unnecessary because both protect DNS. In reality, they address different security concerns. DoH encrypts communication between the DNS client and resolver, protecting queries during transport. However, encryption alone does not prove that the DNS records returned are authentic. DNSSEC provides validation of DNS data, which DoH does not replace. RFC 8484, Section 9, "Security Considerations," explicitly explains that the two protocols solve different problems and remain compatible. Therefore, a secure national login service should not treat DoH as a substitute for DNSSEC validation.
## Open Question
How can a national digital login service select a trustworthy DoH resolver while ensuring DNSSEC validation, protecting citizens' privacy, and maintaining reliable access during network outages?
