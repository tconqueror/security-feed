# Hackers Breach Evertec‑Sinqia: Attempted $130 M Pix Heist

![Hackers breach fintech firm in attempted $130M bank heist](https://www.bleepstatic.com/content/hl-images/2024/02/06/money-bill.jpg)

---

## 1. What Happened

* **Target:**  
  * **Evertec** – a public fintech giant that serves Latin America, Puerto Rico, and the Caribbean.  
  * **Sinqia S.A.** – Evertec’s Brazilian subsidiary, acquired in 2023, headquartered in São Paulo and specializes in financial software and IT services.

* **Attack window:**  
  * **August 29, 2025** – unauthorized activity detected in Sinqia’s Pix environment (the Brazilian real‑time payment system).

* **Severity:**  
  * Hackers attempted to move **$130 million** through two bank‑to‑bank transfers.  
  * Part of the sum was already recovered, but the exact amount remains undisclosed.

---

## 2. Tech‑Staging of the Breach

| Item | Detail |
|------|--------|
| **System** | Pix – Brazil’s instant payment network (launched Nov 2020). |
| **Entry vector** | Stolen credentials belonging to an IT‑vendor account. |
| **Scope** | Only Sinqia’s Pix environment; no evidence of personal data exposure. |

> “On **August 29, 2025**, Sinqia S.A., a Brazilian subsidiary of EVERTEC, Inc., identified unauthorized activity in its environment of the Brazilian Central Bank real‑time payment system known as Pix,” — [SEC filing](https://www.sec.gov/Archives/edgar/data/1559865/000155986525000043/evtc-20250829.htm).

> “Upon detecting the incident, and in accordance with its incident response protocol, Sinqia halted transaction processing in its Pix environment and began working with outside cybersecurity forensics experts.”

---

## 3. Key Stakeholders

| Player | Role | Notable Points |
|--------|------|----------------|
| **Evertec** | Parent company | Disclosed breach via SEC filing. |
| **Sinqia S.A.** | Brazilian subsidiary | Primary victim; halted Pix operations. |
| **Central Bank of Brazil** | Regulator | Revoked Sinqia’s Pix access; overseeing restoration. |
| **HSBC** | One of the targeted banks | Local media implied an HSBC connection; the bank denied any impact on customers. |
| **Cibersecurity Forensics** | External responders | Engaged by Sinqia post‑incident. |

---

## 4. Impact Assessment

* **Financial** – $130 M attempted transfer; partial recovery; exact losses unspecified.  
* **Operational** – Sinqia’s Pix services were shut down; 24 Brazilian financial institutions affected.  
* **Reputational** – “Financial and reputational impact… are not yet known and could be material.” – Evertec.  
* **Data** – No evidence of personal data exposure.  

---

## 5. Immediate Response & Restoration

1. **Incident detection** – Sinqia flagged unauthorized activity on August 29.  
2. **Containment** – Immediate halt of Pix transaction processing.  
3. **Investigation** – Forensics engaged; stolen credentials traced back to an IT‑vendor account.  
4. **Regulatory coordination** – Central Bank revoked Sinqia’s Pix access; Sinqia is actively restoring it.  
5. **Communications** – Evertec released statements; HSBC issued clarifications on customer safety.

---

## 6. Current Status

| Item | Status |
|------|--------|
| **Pix access** | Revoked; under restoration | 
| **Recovered funds** | Partial recovery; amount unknown |
| **Legal/regulatory** | Ongoing investigation; no evidence of data breach |
| **Future resilience** | Evertec emphasizes unknown internal control impact; no concrete remedial plan yet publicly disclosed |

---

## 7. Take‑away

- The attack leveraged stolen vendor credentials to infiltrate a high‑volume fintech payment platform, threatening a sizeable cross‑border money transfer.  
- While no customer funds were ultimately moved and no personal data was exposed, the event underlines the critical need for robust third‑party credential management and continuous monitoring of payment systems.  
- Evertec and Sinqia remain under regulator scrutiny as they resume Pix operations and assess potential internal control deficiencies.  

---