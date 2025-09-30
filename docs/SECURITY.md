# Sneaker Resale Risk Scoring Aggregator - Security Notes

## 🎯 Purpose
This document outlines **security considerations** for the Sneaker Resale Risk Scoring Aggregator. Since the platform aggregates marketplace data, stores user searches, and applies AI scoring, **security and data integrity** are critical.

---

## 🔑 Core Risks

### 1. API Keys & Secrets
- **Collected:** API keys (eBay, Grailed, StockX, etc.), DB credentials.
- **Risks:** Exposure could lead to API abuse or DB breach.
- **Mitigations:**
  - Store secrets in `.env` files (never committed).
  - Rotate API keys regularly.
  - Use environment variables in deployment pipelines.

### 2. User Data
- **Collected:** Search queries, saved favorites, alert preferences.
- **Risks:** Leak could expose user interests or activity.
- **Mitigations:**
  - Encrypt sensitive user preferences at rest.
  - Restrict access to authorized users only.
  - Apply least-privilege access policies.

### 3. Listings Data
- **Collected:** Public marketplace data (prices, images, sellers).
- **Risks:** Incomplete/malformed data could corrupt DB; scraping may trigger rate-limits.
- **Mitigations:**
  - Input validation & sanitization before DB insert.
  - Use caching layers to reduce API load.
  - Respect rate limits and platform ToS.

### 4. AI Risk Scoring
- **Collected:** Sneaker images, seller metadata, prices.
- **Risks:**
  - False positives/negatives damaging trust.
  - Poisoned input (malicious images or metadata).
- **Mitigations:**
  - Clearly disclaim scores as *estimates, not guarantees*.
  - Run image sanitization before ML inference.
  - Use ensemble scoring (image + metadata) to reduce bias.

### 5. Deployment & Hosting
- **Platform:** Vercel (frontend), Render/VPS (backend).
- **Risks:** Config leaks, unauthorized access, DDoS.
- **Mitigations:**
  - HTTPS enforced.
  - Strict CORS policies.
  - Firewalls + rate limiting on backend routes.

---

## 📋 Security-by-Design Principles

1. **Least Privilege** → All API routes and DB access scoped by role.
2. **Zero Secrets in Repo** → All credentials externalized to `.env`.
3. **Transparency** → Scores shown with *reason codes* to prevent blind trust.
4. **Auditability** → Log API calls, DB writes, and scoring outputs.
5. **Defense in Depth** → Combine metadata + AI scoring, alerts, and monitoring.
6. **Fail-Safe Defaults** → If risk scoring fails, mark as *Unknown* rather than safe.

---

## ⚡ Gaps & Future Improvements
- Automated penetration testing for API routes.
- Intrusion detection & anomaly monitoring.
- Anti-scraping bypass compliance checks.
- Expanded red-team testing on ML model robustness.
- Explore encrypted user preference storage (client-side first).

---

## ✅ Recruiter-Facing Takeaway
This project applies **practical, production-grade security practices** to sneaker resale aggregation:

- Secrets handled securely with `.env` & key rotation.  
- User preferences protected with least-privilege and encryption.  
- AI scores wrapped with transparency + disclaimers.  
- Defense-in-depth applied across scraping, APIs, DB, and ML inference.  

Even at MVP stage, security is built in from day one.
