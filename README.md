# 🚗 Corporate Garage Management System## 📌 Descrizione del ProgettoPiattaforma gestionale per un parco auto aziendale. Il sistema centralizza il monitoraggio di circa 50 veicoli, permettendo la gestione di chilometraggio, carburante e manutenzioni, con accessi differenziati tra Amministrazione e Dipendenti.

---
## 🔐 Logica dei Permessi (RBAC)
Il sistema implementa una **Row-Level Security** basata sull'utente loggato:
### 👑 Amministratore (Boss)- **Accesso:** Totale su tutti i 50 veicoli.- **Poteri:** Può creare, modificare ed **eliminare** qualsiasi auto o evento.- **Esclusività:** Gestisce l'assegnazione dell'auto (`owner`) e la foto ufficiale (`imageURL`).
### 👤 Dipendente (User)- **Accesso:** Vede **solo** l'auto a lui assegnata.- **Poteri:** Modifica esclusivamente i dati dinamici (Km, Benzina, Eventi).- **Restrizioni:** Non può eliminare il veicolo né modificare dati anagrafici o foto.

---
## 🛠️ Stack Tecnologico- **Backend:** SAP Cloud Application Programming Model (CAP) - Node.js.- **Database:** SQLite (per sviluppo).- **Frontend:** SAP Fiori Elements (List Report & Object Page).- **Sicurezza:** Mock Authentication con permessi granulari via `@restrict`.

---
## 📊 Struttura Dati
| Entità | Descrizione |
| :--- | :--- |
| **Cars** | Anagrafica veicolo, proprietario, foto, km e carburante. |
| **CarEvents** | Storico interventi (Tagliandi, gomme, guasti). |
| **Manufacturers** | Elenco dei brand automobilistici. |



---
## 🚀 Passaggi

fare npm init -y
npm install @sap/cds
npm install @cap-js/postgres