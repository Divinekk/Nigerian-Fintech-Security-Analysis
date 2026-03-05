## 🔐 Nigerian Fintech Security Analysis

Research-backed analysis of security vulnerabilities in Nigerian financial technology systems, with proposed solutions.


> "₦52.26 billion lost to fraud in 2024. The problem isn't technology - 
> it's implementation."

---

## 📚 About This Research

This repository documents findings from my undergraduate thesis 
**"Cryptanalysis of Cryptographic Algorithms in Nigerian Banking 
Security"** which was recognized as the **Best Presenter** at TDK Conference 2025, University of Debrecen, Hungary.

The research analyzes cryptographic implementations in Nigerian 
banking and fintech systems, identifying critical vulnerabilities 
and proposing practical solutions.

**[📄 Read Full Research Paper](./TDK_Banking_Security_Research.pdf)**

---

## 🎯 Key Research Areas

### 1. Password Hashing Algorithms
**Compared:** BCrypt vs Argon2 vs SHA-256  
**Recommendation:** Argon2 with parallelism for Nigerian fintech  
**Why:** Balances security with server costs in emerging markets

### 2. Authentication & Authorization
**Compared:** JWT+HMAC vs JWT+RSA256 vs JWT+EdDSA vs JWT+AES-GCM  
**Critical Finding:** Nigerian APIs vulnerable to BOLA  
**Recommendation:** Service-layer ownership validation

### 3. One-Time Password Systems
**Compared:** HOTP vs TOTP  
**Vulnerability:** SMS-based OTP susceptible to SIM-swap attacks  
**Recommendation:** TOTP with push notifications

### 4. Encryption at Rest
**Compared:** AES-CBC vs AES-GCM  
**Recommendation:** AES-256-GCM for financial data  
**Why:** Built-in authentication prevents tampering

---

## 📊 Case Studies: Real-World Nigerian Incidents

### [FSDH Insider Fraud (2026)][(./case-studies/fsdh-insider-fraud-2026.md)](https://www.efcc.gov.ng/news/efcc-arraigns-bankers-for-alleged-30666781-50250-fraud-in-lagos) 
Two bank officials arraigned for ₦527 million SWIFT fraud. Analysis of insider threats and access control failures

### [GTBank Cyberattack ](https://businessday.ng/companies/article/gtbanks-cyber-attack-a-wake-up-call-for-nigerian-banks-amid-recapitalisation-efforts/)
Analysis of the attack that disrupted services for millions of users.

### [UBA/Netflix OTP Abuse Case](https://pmnewsnigeria.com/2024/05/21/nefgad-drags-netflix-old-generation-bank-to-court-over-abuse-of-otp-customers-account-details/)
How weak OTP implementation led to unauthorized recurring charges.


### [Digital Payment Fraud Statistics (2024-2025)](https://nibss-plc.com.ng/digital-payment-fraud-drops-51-to-n25-85b-lagos-accounts-for-63/)
₦52.26 billion lost in 2024, declined 51% to ₦25.85 billion in 2025 
(NIBSS). Analysis of the improvement and remaining challenges.

*This is an ongoing research repository. Case studies added regularly 
as incidents are analyzed.*


---

## 🛡️ Proposed Security Framework

### For Banking Institutions
1. **Password Storage:** Migrate to Argon2 (cost: minimal, impact: high)
2. **API Authorization:** Implement BOLA prevention at service layer
3. **OTP Systems:** Replace SMS with TOTP + push notifications
4. **Encryption:** Adopt AES-256-GCM for sensitive data at rest
5. **Monitoring:** Real-time anomaly detection systems

### For Fintech Startups
1. **Start Secure:** Build with security-first architecture
2. **Use Proven Standards:** Don't reinvent cryptography
3. **Regular Audits:** Quarterly security assessments
4. **Employee Training:** Security awareness programs
5. **Incident Response:** Pre-planned breach protocols

### For Regulatory Bodies
1. **Minimum Standards:** Mandate baseline security requirements
2. **Penetration Testing:** Annual third-party security audits
3. **Incident Reporting:** Mandatory breach disclosure framework
4. **Public Awareness:** Consumer education campaigns
5. **Enforcement:** Penalties for non-compliance

---

## 💻 Implementation Examples

See working implementations in my projects:

**[Vault-API](https://github.com/Divinekk/Vault-API)**
- BCrypt password hashing (cost factor 12)
- JWT authentication with HS256
- BOLA prevention at service layer
- AES-256-GCM encryption for account balances

**[LedgerLoom](https://github.com/Divinekk/LedgerLoom)**
- Optimistic locking for race condition prevention
- Atomic transactions with @Transactional
- High-concurrency transaction handling

---

## 📈 Impact Metrics

**Problem Scale:**
- ₦52.26 billion lost to fraud in 2024 (Blueprint Newspapers)
- 70+ million Nigerians using fintech services (Moniepoint alone)
- 1.3 million phishing attempts in Nigeria (H1 2023, Check Point Research)

**If Recommendations Adopted:**
- Estimated 60-80% reduction in credential-based attacks
- 90%+ reduction in BOLA-related data breaches
- 50%+ reduction in OTP-based fraud

---

## 📝 Publications & Presentations

### Research Papers
- **TDK Conference 2025** - "Cryptanalysis of Cryptographic Algorithms 
  in Nigerian Banking Security" (Best Presenter Award)

### Blog Articles
- [Why API Security is the Backbone of Nigerian Fintech](https://medium.com/@divine.ogbonna.chisom/why-api-security-is-the-backbone-of-nigerian-fintech-lessons-from-building-a-secure-banking-3cc5ed26c498)
- [How I Prevented BOLA Vulnerabilities in a Banking API](https://medium.com/@divine.ogbonna.chisom/how-i-prevented-bola-vulnerabilities-in-a-banking-api-91418a78245b)
- [Completing the Security Trilogy: AES Encryption, Testing and Deployment](https://medium.com/@divine.ogbonna.chisom/completing-the-security-trilogy-encryption-testing-and-deployment-668e87e93d33)

---

## 🔬 Research Methodology

**Approach:**
1. Literature review of cryptographic algorithms
2. Comparative performance analysis (speed, memory, security)
3. Real-world case study analysis
4. Implementation and testing in Vault-API
5. Gap identification and solution proposal

**Tools Used:**
- Java Spring Boot for implementation
- OWASP Top 10 for vulnerability framework
- Nigerian banking fraud reports for context
- Academic papers on cryptography

---

## 🤝 Contributing

This is an ongoing research project. Contributions welcome:
- Additional Nigerian fintech case studies
- Security incident reports
- Implementation feedback
- Academic critique

**How to contribute:**
1. Fork this repository
2. Create your case study/analysis in markdown
3. Submit a pull request
4. Include sources and evidence

---

## 📬 Contact

**Divine Ogbonna**  
Security-Focused Backend Engineer | Fintech Security Researcher

- **GitHub:** [@Divinekk](https://github.com/Divinekk)
- **LinkedIn:** [Connect](https://linkedin.com/in/divine-ogbonna)
- **Medium:** [Read My Articles](https://medium.com/@divine.ogbonna.chisom)

For academic collaboration or industry consultation on Nigerian 
fintech security, please reach out.

---

## 📄 License

This research is shared under MIT License for educational and 
non-commercial use. Commercial applications require attribution.

---

**Built to bridge the gap between cybersecurity research and 
practical implementation in Nigerian fintech.**
