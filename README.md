# Sneaker Resale Risk Scoring Aggregator 👟  

A **full-stack web app** that aggregates sneaker resale listings across multiple platforms and applies a **risk scoring system** to help buyers find the **best-value and most trustworthy** deals.  

---

## ✨ Features (Planned & In Progress)

- 🔎 **Multi-platform search** → Aggregates listings from eBay, Depop, Grailed, StockX, GOAT, and Poshmark.  
- 📊 **Risk Scoring Engine** → Combines seller reputation, price anomaly detection, and image similarity (CLIP embeddings) to estimate listing risk.  
- ⭐ **Favorites & Alerts** → Save sneakers and get notified when a new deal matches your criteria.  
- 🖥️ **Frontend UI** → React interface with search, filters, and saved items dashboard.  
- 📂 **Backend API** → Node.js/Express server with MongoDB persistence.  

---

## 🛠 Tech Stack

**Core**  
- Frontend: React (in progress), Tailwind CSS  
- Backend: Node.js, Express  
- Database: MongoDB + Mongoose  

**AI / Risk Scoring**  
- OpenAI CLIP (image similarity)  
- TensorFlow.js (prototyping)  
- Price anomaly detection algorithms  

**Infrastructure**  
- Vercel (frontend hosting)  
- Render/VPS (backend hosting)  
- dotenv for secrets management  
- GitHub Actions (CI/CD – planned)  

---

## 📊 Impact (Expected)

⚡ **Transparency in sneaker reselling** → Helps buyers avoid scams.  
📌 **Aggregates scattered marketplaces** → One dashboard for all major sneaker resale sites.  
🔐 **Risk-aware design** → Shows *why* a listing is flagged as High / Medium / Low risk.  
🚀 **Portfolio-ready** → Demonstrates full-stack + AI integration beyond automation bots.  

---

## 📂 Repository Structure (Planned)

```text
sneaker-risk-aggregator/
├── client/                 # React frontend
│   ├── src/
│   └── public/
├── server/                 # Node.js backend
│   ├── routes/
│   ├── models/
│   └── utils/
├── docs/                   # Documentation
│   ├── ARCHITECTURE.md
│   ├── SECURITY.md
│   └── INTEGRATIONS.md
├── package.json
└── README.md
```

---

## 📖 Additional Documentation

- [ARCHITECTURE.md](./docs/ARCHITECTURE.md) → System design & data flow  
- [INTEGRATIONS.md](./docs/INTEGRATIONS.md) → eBay, Depop, Grailed, StockX APIs  
- [SECURITY.md](./docs/SECURITY.md) → Secrets, API keys, and user data handling  

---

📌 **Status:** Currently building MVP (single-platform integration + basic risk scoring).  
Live demo + deployment coming soon.
