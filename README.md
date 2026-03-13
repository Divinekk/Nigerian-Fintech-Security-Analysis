# Nigerian Fintech Security Analysis

Research-backed cryptanalysis of authentication and encryption protocols used in Nigerian banking systems, with documented vulnerabilities and proposed improvements.

> "52.26 billion naira lost to fraud in 2024. The problem is not the technology. It is the implementation."

---

## About This Research

**"Cryptanalysis of Cryptographic Algorithms in Nigerian Banking Security: JWT, HMAC, RSA256, AES, HOTP, TOTP and BCrypt"**
University of Debrecen, 2025. Best Presenter, TDK Research Conference, Informatics Section.

**[Read the Full Paper](./TDK_Banking_Security_Research.pdf)**

The research reviews existing cryptographic literature, benchmarks algorithms across five metrics, and identifies implementation gaps specific to Nigerian banking infrastructure. No direct code implementation was done within the thesis itself (see p.43). Vault-API was built afterwards as a standalone implementation of the findings.

---

## Key Findings

**Password Hashing**
BCrypt's default cost factor of 10 is too low for modern brute-force hardware. Argon2 is the stronger recommendation but BCrypt at cost factor 12 is the pragmatic minimum.

**JWT Authentication**
JWT with AES-GCM delivers the best performance and lowest overhead across benchmarks. Nigerian APIs are broadly exposed to BOLA (OWASP API Security Top 1) due to missing service-layer ownership validation.

**One-Time Passwords**
SMS-based OTP is vulnerable to SIM-swap attacks, documented in the UBA/Netflix case below. TOTP with push notification fallback is the recommended replacement.

**Encryption at Rest**
AES-256-GCM provides confidentiality and integrity in one operation. AES-CBC requires a separate HMAC and should not be used for sensitive financial data.

---

## Case Studies

**[GTBank Website Attack, August 2024](https://businessday.ng/companies/article/gtbanks-cyber-attack-a-wake-up-call-for-nigerian-banks-amid-recapitalisation-efforts/)**
GTBank confirmed an attempted hack on its website one day after renewing its domain, and days after closing a 400.5 billion naira share offer. No customer data was compromised. Relevant to: DNS-layer attack vectors, domain security hygiene, and how high-value financial events create elevated threat windows.

**[UBA/Netflix OTP Abuse](./TDK_Banking_Security_Research.pdf)**
NEFGAD documented unauthorized recurring debits from a Nigerian customer's account through exploited OTP flows. Single-use OTPs were not enforced per transaction, allowing repeated charges under a single OTP event.

**[FSDH Insider Fraud, EFCC 2026](./TDK_Banking_Security_Research.pdf)**
Two bank officials arraigned for 527 million naira SWIFT fraud. Insufficient service-layer authorization checks enabled insider exploitation at scale. A direct real-world consequence of the BOLA vulnerabilities analyzed in this research.

**[Digital Payment Fraud Trend, 2024 to 2025](./TDK_Banking_Security_Research.pdf)**
52.26 billion naira lost in 2024, declining 51% to 25.85 billion naira in 2025 (NIBSS). Analysis of what drove the improvement and where structural vulnerabilities remain.

---

## Implementations

The research is theoretical. These two projects implement the findings in code.

**[Vault-API](https://github.com/Divinekk/Vault-API)**
Secure banking backend built directly from the thesis recommendations.
BCrypt at cost factor 12, JWT authentication, BOLA prevention at the service layer, AES-256-GCM for account balances at rest.

**[LedgerLoom](https://github.com/Divinekk/LedgerLoom)**
High-concurrency transaction engine solving the Double-Spending Problem.
Optimistic locking via JPA @Version, atomic fund transfers with @Transactional.

---

## Related Writing

- [Why API Security is the Backbone of Nigerian Fintech](https://medium.com/@divine.ogbonna.chisom)
- [How I Prevented BOLA Vulnerabilities in a Banking API](https://medium.com/@divine.ogbonna.chisom)
- [Completing the Security Trilogy: AES Encryption, Testing and Deployment](https://medium.com/@divine.ogbonna.chisom)

---

## Contact

Divine Ogbonna
[GitHub](https://github.com/Divinekk) | [LinkedIn](https://www.linkedin.com/in/ogbonna-divine-a81453242/) | [Medium](https://medium.com/@divine.ogbonna.chisom)

MIT License. Commercial use requires attribution.
