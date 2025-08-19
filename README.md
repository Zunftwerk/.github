# 🌱 Zunftwerk

> **Faire Arbeitszeiterfassung – nachhaltig, transparent, zukunftssicher.**  
> Ein SaaS für den DACH-Raum (und darüber hinaus).

---

## 🚀 Vision

Zunftwerk ist eine **nachhaltige Zeiterfassungsplattform**, die moderne Technologie mit **Green-First-Ansatz** verbindet.  
Wir bauen eine Lösung, die:

- ✅ **Arbeitszeiten korrekt & gesetzeskonform** erfasst (EU/DACH-Standards)  
- ✅ **Unveränderbare Audit-Trails** ermöglicht, ohne unnötige Komplexität  
- ✅ **Fair & transparent** mit Kundendaten umgeht – Daten gehören dem Kunden  
- ✅ **Ressourcenschonend & grün** betrieben wird (Öko-Hosting, effizienter Code)  

---

## 🛠️ Architektur (Kurzüberblick)

```
            ┌───────────────────┐
            │ Flutter Mobile-App │
            └───────▲───────────┘
                    │
                    ▼
      ┌───────────────────────────────┐
      │   🌐 Web Admin (SvelteKit)    │
      └───────────────▲───────────────┘
                      │
                      ▼
        ┌─────────────────────────┐
        │   API Backend (Deno)    │
        │   - Auth & RBAC         │
        │   - Time Entries        │
        │   - Audit Logs          │
        └───────────▲─────────────┘
                    │
                    ▼
        ┌─────────────────────────┐
        │ Worker (Exports, Jobs)  │
        │ - CSV, PDF, ZIP         │
        └───────────▲─────────────┘
                    │
                    ▼
        ┌─────────────────────────┐
        │ PostgreSQL + S3 Storage │
        └─────────────────────────┘
```

---

## 📦 Monorepo Struktur

```bash
zunftwerk/
├─ apps/
│  ├─ api/         # Deno REST API
│  ├─ worker/      # Deno Batch-Worker (Exports/Reports)
│  ├─ admin/       # Web Admin PWA (SvelteKit + Tailwind)
│  └─ mobile/      # Flutter Mobile App
│
├─ packages/
│  ├─ db/          # SQL Migrations, Seeds, DB Client
│  ├─ core/        # Shared TS-Types & Utilities
│  ├─ pdf/         # PDF Generator Bausteine
│  └─ csv/         # CSV Export Utilities
│
├─ infra/          # Deployment (Docker, Terraform, Ansible)
├─ ops/            # CI/CD, Monitoring, Runbooks
└─ docs/           # ADRs, Architektur-Entscheidungen
```

---

## ⚡ Features (MVP)

- ⏱️ Einfache **Zeiterfassung** (Start/Stop, Projekte, Pausen)  
- 📊 **Auswertungen & Reports** (CSV/PDF)  
- 📝 **Audit-Trail** für Nachvollziehbarkeit  
- 📱 **Offline-fähige Flutter App**  
- 🌍 **Admin-Dashboard** für Manager & Teams  
- 🔐 **DSGVO-konform** mit klarer Datenhoheit  

---

## 💶 Preismodell (geplant)

- **Free** → 1 Nutzer, Basisfunktionen, Exporte  
- **Starter** → bis 10 Nutzer, alle Standardfunktionen (~19 €/Monat)  
- **Team** → bis 50 Nutzer, Reports & Audit (~49 €/Monat)  
- **Business** → bis 100 Nutzer, API & SLA (~99 €/Monat)  

---

## 🌍 Nachhaltigkeit & Fairness

- ♻️ Green Hosting (Ökostrom, effizienter Code)  
- 🖥️ Minimale Serverlast durch schlanke Architektur  
- 🌱 Für jede X Arbeitsstunden pflanzen wir einen Baum  
- 🤝 Kundendaten gehören immer dem Kunden  

---

## 🛠️ Development Setup

```bash
# 1. Postgres + Minio starten
docker compose -f infra/docker-compose.dev.yml up -d

# 2. .env erstellen
cp .env.example .env

# 3. Migration ausführen
make db-migrate

# 4. Starten
make dev
```

---

## 🤝 Contribution

Wir lieben **Clean Code** und **Transparenz**:

- Commit-Konvention: [Conventional Commits](https://www.conventionalcommits.org)  
- Tests Pflicht für neue Features  
- Jede Architektur-Entscheidung → [ADR](docs/adr)

---

## 👋 Kontakt

**Zunftwerk**  
Faire Arbeitszeit – nachhaltig und modern.  
🌐 [zunftwerk.com](https://zunftwerk.com)
