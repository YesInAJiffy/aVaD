


# SAP Ariba in Simple Terms

**SAP Ariba** is a corporate purchasing and supplier-management platform. Think of it as five systems rolled into one:

* An internal shopping portal
* An approval system
* A purchase-order (PO) system
* A supplier portal
* An invoice-matching system

It helps a company control:

* **What** employees purchase
* **Which** suppliers they use
* **Who** must approve the purchase
* **Whether** the purchase follows a contract
* **Whether** goods or services were actually received
* **Whether** the supplier’s invoice should be paid

Ariba covers the complete **Source-to-Pay (S2P)** lifecycle—from selecting suppliers and negotiating contracts through ordering, receiving, invoicing, and payment processing.

---

## 1. The Big Split: Upstream (S2C) vs. Downstream (P2P)

**Source-to-Pay (S2P)** is the entire lifecycle, divided into two halves split at the **signed contract**. Everything before the contract is **Upstream (Sourcing)**; everything after is **Downstream (Purchasing & Payment)**.

```
========================================================================================
                               SOURCE-TO-PAY (S2P) LIFECYCLE
========================================================================================

  UPSTREAM: Source-to-Contract (S2C)        │    DOWNSTREAM: Procure-to-Pay (P2P)
  (Strategic Sourcing • Occasional)         │    (Transactional Buying • Daily)
                                            │
  ┌───────────────────────────────────┐     │    ┌───────────────────────────────────┐
  │ • Spend Analysis                  │     │    │ • Purchase Requisition & Approval │
  │ • Supplier Discovery & Risk Check │     │    │ • Purchase Order (PO) Issued      │
  │ • Sourcing Event (RFI/RFP/Bid)    │     │    │ • Goods Receipt / Service Sheet   │
  │ • Negotiation & Award             │     │    │ • Supplier Invoice & 3-Way Match  │
  │ • Contract / SoW Signed           │     │    │ • ERP Payment Execution           │
  └─────────────────┬─────────────────┘     │    └─────────────────▲─────────────────┘
                    │                       │                      │
                    └──────────► [ SIGNED CONTRACT ] ──────────────┘
                                 (The Handoff Bridge)
                                            │
                    ◄─────────── Spend & Compliance Data ──────────┘
                         (Feeds back into future Spend Analysis)
========================================================================================

```

---

## 2. End-to-End Flow (Showing the Sourcing Detour)

Everyday employees start in **Downstream (P2P)**. If an item is already on a pre-approved catalog, it stays in P2P from start to finish. If it is high-value or lacks an existing contract, Ariba pauses the request and **detours into Upstream (S2C)** for sourcing and contracting before returning to P2P to issue the Purchase Order.

```
     DOWNSTREAM: Procure-to-Pay (P2P)          │      UPSTREAM: Source-to-Contract (S2C)
     (Where Employees & AP Operate)            │      (Where Strategic Sourcing Operates)
───────────────────────────────────────────────┼───────────────────────────────────────────
                                               │
  [Business Need]                              │
         │                                     │
         ▼                                     │
  ┌─────────────────────┐                      │
  │ Purchase Requisition│                      │
  │ (What, Cost Center) │                      │
  └──────┬───────┬──────┘                      │
         │       │                             │
  Routine│       │ New / High-Value Spend      │
  Buy    │       └───────(Detour to S2C)───────┼──► ┌──────────────────────────┐
         │                                     │    │ 1. Sourcing Request /    │
         │                                     │    │    RFI / RFP / Bid         │
         │                                     │    └────────────┬─────────────┘
         │                                     │                 │
         │                                     │                 ▼
         │                                     │    ┌──────────────────────────┐
         │                                     │    │ 2. Negotiation & Award   │
         │                                     │    └────────────┬─────────────┘
         │                                     │                 │
         │                                     │                 ▼
         │                                     │    ┌──────────────────────────┐
         │  ┌──────(Contract / SoW Signed)─────┼────┤ 3. Contract & SoW Signed │
         │  │                                  │    │    (Ariba Contracts)     │
         ▼  ▼                                  │    └──────────────────────────┘
  ┌─────────────────────┐                      │
  │ Rule-Based Approvals│                      │
  │ (Manager/Finance/IT)│                      │
  └──────────┬──────────┘                      │
             │                                 │
             ▼                                 │
  ┌─────────────────────┐                      │
  │ Purchase Order (PO) │                      │
  │ Sent via Network    │                      │
  └──────────┬──────────┘                      │
             │                                 │
      ┌──────┴───────────────────┐             │
      │ (Path splits by type)    │             │
      ▼                          ▼             │
  [ GOODS ]               [ SERVICES ]         │
  Goods Receipt (GR)      Service Entry Sheet  │
  logged on delivery      (SES) / Timesheet    │
      │                   approved by PM       │
      └──────┬───────────────────┘             │
             │                                 │
             ▼                                 │
  ┌─────────────────────┐                      │
  │ Supplier Invoice &  │                      │
  │ Automated 3-Way     │                      │
  │ Match (PO=GR=Bill)  │                      │
  └──────────┬──────────┘                      │
             │                                 │
             ▼                                 │
  ┌─────────────────────┐                      │
  │ ERP Payment         │                      │
  │ (SAP S/4HANA/Oracle)│                      │
  └─────────────────────┘                      │
───────────────────────────────────────────────┴───────────────────────────────────────────

```
<img width="896" height="1200" alt="Gemini_Generated_Image_joutxgjoutxgjout" src="https://github.com/user-attachments/assets/c4b5832e-f5e5-46a4-9dba-000f1f571e13" />


<img width="768" height="1376" alt="Gemini_Generated_Image_25srbk25srbk25sr" src="https://github.com/user-attachments/assets/ee44a6cb-d582-40b6-a569-18d097f82539" />

---

## 3. Upstream: Source-to-Contract (Strategic Sourcing)

This is where procurement decides **who** to buy from and **on what terms**. It happens occasionally per category or major project, not for every routine purchase.

* **Spend Analysis:** Reviewing what the company spends, with whom, and where consolidating vendors can save money.
* **Supplier Discovery & Qualification:** Finding candidates and vetting their financial health, cybersecurity, and compliance risk (*Supplier Lifecycle & Performance* and *Supplier Risk*).
* **Sourcing Events:** Running competitive bids—**RFI** (Information), **RFP** (Proposal), **RFQ** (Quote), or **Reverse Auctions**—where invited suppliers bid online and are scored on price, technical fit, and risk.
* **Negotiation & Award:** Selecting the winning supplier and agreeing on hourly rate cards, SLAs, term, and liability.
* **Contract & SoW Authoring:** Capturing legal terms in a **Master Contract (MSA)** and project deliverables in a **Statement of Work (SoW)** inside *Ariba Contracts*, tracking renewal dates and obligations.

---

## 4. Downstream: Procure-to-Pay (Transactional Buying)

This is the day-to-day execution of buying under agreed terms. It runs continuously at high volume.

* **Requisition & Approval:** An employee or project manager raises a request detailing what is needed, the cost center/project code, and estimated cost. Approval routing is rule-based (dollar thresholds, category, department, plus InfoSec or Legal reviews where required).
* **Purchase Order (PO):** Approved requisitions convert to POs and go to the supplier via the **SAP Business Network** (formerly Ariba Network), referencing the upstream contract so negotiated rates apply. Routine catalog items skip sourcing and go straight here.
* **Receiving (Goods vs. Services):**
* **Goods:** The buyer logs a **Goods Receipt (GR)** confirming physical delivery.
* **Services:** The vendor logs hours or milestones in a **Service Entry Sheet (SES)**, which the project manager approves.


* **Invoice & 3-Way Match:** The supplier submits an invoice through the network. Ariba matches it against the **PO** and **Receipt/SES**. Clean matches flow to payment; discrepancies go to an exception queue.
* **Payment:** Released through the company's core ERP (such as **SAP S/4HANA** or **Oracle**).

---

## 5. How Upstream and Downstream Connect

* **The Contract is the Bridge:** Upstream (**S2C**) produces the Master Contract and SoW; Downstream (**P2P**) consumes them. When a PO pulls its prices and terms from an active contract, that is **"buying on contract."**
* **Data Flows Back Upstream:** Downstream (**P2P**) generates actual spend data, feeding the next round of Spend Analysis and exposing off-contract purchases (**maverick or tail spend**) so sourcing knows what to renegotiate next.
* **Why Companies Treat Them Separately:**
* **Different Owners:** S2C is run by Category Managers and Legal; P2P is run by Procurement Operations, Accounts Payable, and everyday employees.
* **Different Cadence:** S2C happens periodically (annually or per major project); P2P happens daily.
* **Different Rollout:** Many companies implement P2P first to control daily purchasing and invoicing, then add S2C later—or vice versa.

---
# Unified Architecture

The reason SAP Ariba feels seamless for both the **client (buying company)** and the **vendor (supplier)** is that they do not email PDFs back and forth or maintain two separate, disconnected databases. Instead, both sides connect to a single, shared cloud hub called the **SAP Business Network** (formerly the Ariba Network).

Think of it like **LinkedIn or a shared banking network**: you and another person each have your own private account and view, but when you send a message or transfer money, the underlying platform translates and delivers it instantaneously in a standardized format.

---

## 1. The Architecture: Two Portals, One Shared Network

While the buyer and supplier log into different interfaces tailored to their roles, every transaction travels across the same central cloud highway using standardized digital documents (**cXML**—Commerce eXtensible Markup Language).

```
  BUYER / CLIENT SIDE                        SHARED CLOUD HUB                      VENDOR / SUPPLIER SIDE
  (SAP Ariba Buying & Sourcing)            (SAP Business Network)                (Ariba Supplier Portal)
┌───────────────────────────────┐        ┌────────────────────────┐        ┌───────────────────────────────┐
│ • Internal Employee Portal    │        │                        │        │ • Single Login for All Clients│
│ • Approval Workflows          │◄──────►│  Standardized cXML     │◄──────►│ • Views RFPs & Submits Bids   │
│ • Connects to Client's ERP    │        │  Document Exchange     │        │ • Receives POs Electronically │
│   (SAP S/4HANA / Oracle)      │        │  & Validation Rules    │        │ • "PO Flip" into Invoices     │
└───────────────────────────────┘        └────────────────────────┘        └───────────────────────────────┘

```

### How Each Side Experiences the Same System

* **The Client (Buyer) Side:** Employees log into their company's private Ariba instance (*Ariba Guided Buying / Buying & Invoicing*), which is branded with their company logo and wired into their internal cost centers, approval chains, and ERP system.
* **The Vendor (Supplier) Side:** Vendors log into the **SAP Business Network Supplier Portal**. Crucially, a vendor only needs **one single account** to do business with *all* of their enterprise clients that use Ariba. Inside that one portal, they see a unified dashboard of every RFP, Purchase Order, Service Entry Sheet, and payment status across all their customers.

---

## 2. How Documents Flow Seamlessly ("No Re-Typing")

Because both sides sit on the same network, data created by one party automatically becomes the starting template for the other party—eliminating manual data entry and human typos:

| Stage | What the Client (Buyer) Does | What Happens on the Network | What the Vendor (Supplier) Sees |
| --- | --- | --- | --- |
| **1. Bidding (RFP)** | Publishes an RFP with line items and pricing tables. | Network notifies invited vendors and opens a secure bidding room. | Opens the exact same pricing table online, fills in their rates, and hits submit. |
| **2. Ordering (PO)** | Approves a requisition; Ariba generates an official **Purchase Order**. | Network converts the PO into standardized cXML and routes it instantly. | Receives the digital PO in their inbox (or directly inside their own ERP) within seconds. |
| **3. Fulfillment (SES / ASN)** | Waits for confirmation that hardware shipped or contractor hours were worked. | Vendor submits a digital **Service Entry Sheet (SES)** or **Advance Ship Notice** against the PO. | Selects the PO, logs hours/milestones, and submits. The client's PM gets an instant approval alert. |
| **4. Billing ("PO Flip")** | Enforces strict rules (e.g., *"Do not allow invoices higher than PO price"*). | Network enforces the client's rules *before* the vendor can even hit "Send." | Clicks **"Create Invoice" (PO Flip)**—Ariba copies all PO/SES line items, prices, and tax codes automatically. |
| **5. Payment Status** | ERP schedules payment after the 3-way match succeeds. | Client's ERP pushes status updates back to the network automatically. | Sees live status changes (*Approved $\rightarrow$ Scheduled $\rightarrow$ Paid*) without calling AP. |

---

## 3. Why This "Uniformity" Prevents Errors

1. **The "PO Flip" Eliminates Discrepancies:** Instead of a vendor's billing team typing up a fresh invoice from scratch (and accidentally using old rates or wrong PO numbers), Ariba lets them **flip** the approved PO or Service Entry Sheet directly into an invoice. Because the numbers are copied straight from the client's own PO, the **3-Way Match** succeeds automatically almost every time.
2. **Real-Time Rule Enforcement (Validation at the Source):** The client's business rules travel across the network to the vendor's screen. If a client's contract says *"Senior Developer rate cannot exceed $120/hr,"* and the vendor tries to type $125/hr on an invoice, the Ariba portal blocks the vendor immediately with an error message—long before it ever reaches the client's Accounts Payable team.
3. **Enterprise-to-Enterprise Integration:** For large IT vendors or hardware suppliers (like Dell or Accenture), they don't even have to log into a web browser—they link their own internal ERP (SAP, Oracle, Salesforce, NetSuite) directly to the SAP Business Network so POs and invoices flow machine-to-machine.

---
<img width="1376" height="768" alt="Gemini_Generated_Image_ma0nqcma0nqcma0n" src="https://github.com/user-attachments/assets/950b897f-55a2-4320-9036-58f01e22353f" />


# MSA vs SoW

* The **Contract (MSA)** is the **"Relationship Rulebook"** (legal, financial, and compliance rules).
* The **Statement of Work (SoW)** is the **"Project Blueprint"** (what is actually being built, delivered, when, and for how much).

---

## 1. How They Work Together (Parent & Child)

In IT and corporate procurement (including SAP Ariba), companies sign **one overarching Contract (MSA)** with a vendor, and then attach **multiple SoWs** underneath it over the years as new projects come up—without having to renegotiate legal terms every single time.

```
┌──────────────────────────────────────────────────────────┐
│           MASTER SERVICES AGREEMENT (MSA / Contract)     │
│  • Payment terms (e.g., Net 30)                          │
│  • Intellectual Property (IP) ownership                  │
│  • Confidentiality (NDA), Liability, & Dispute rules     │
└────────────────────────────┬─────────────────────────────┘
                             │ (Governs all work below)
         ┌───────────────────┼───────────────────┐
         ▼                   ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│     SoW #1      │ │     SoW #2      │ │     SoW #3      │
│ Cloud Migration │ │ Mobile App UI   │ │ 24/7 Support    │
│ • Scope & Tasks │ │ • Scope & Tasks │ │ • Scope & Tasks │
│ • Milestones    │ │ • Deliverables  │ │ • SLA & Rates   │
│ • Price: $150k  │ │ • Price: $60k   │ │ • Price: $10k/mo│
└─────────────────┘ └─────────────────┘ └─────────────────┘

```
<img width="1376" height="768" alt="Gemini_Generated_Image_u322y3u322y3u322" src="https://github.com/user-attachments/assets/fc235667-9775-4f4c-86b2-1f0eeb05a270" />

---

## 2. Key Differences Side-by-Side

| Feature | Contract (Master Services Agreement) | Statement of Work (SoW) |
| --- | --- | --- |
| **Core Purpose** | Establishes the legal business relationship | Defines a specific project, service, or engagement |
| **What It Contains** | Liability caps, IP rights, confidentiality, termination clauses, payment terms (e.g., Net 30), and governing law | Project scope, deliverables, timelines, milestones, acceptance criteria, resource roles, and exact pricing |
| **Who Negotiates It** | Legal teams, Procurement, and Executives | Project Managers, Engineering/IT Leads, and Procurement |
| **Lifespan** | Long-term (typically 3 to 5 years, or evergreen) | Short-to-medium term (lasts only until that specific project finishes) |
| **Frequency** | Signed once per vendor | Created for every new project or batch of contractors |

---

## 3. How SAP Ariba Handles Them

Inside **SAP Ariba Contracts**, this parent-child structure is built directly into the system:

1. **Main Agreement (The MSA):** Stored in Ariba Contracts as the top-level **Master Agreement**. It tracks expiration dates, insurance certificates, and negotiated **rate cards** (e.g., *"Senior Java Developer = $120/hr"*).
2. **Sub-Agreements / Orders (The SoW):** Created as a **Sub-Agreement** linked to that Master Agreement (or attached directly to a **Service Purchase Order**).
3. **Execution:** When the vendor submits a **Service Entry Sheet (SES)** or invoice in Ariba, Ariba checks the **SoW** for the milestone/hours and the **Master Contract** for the payment terms and approved rate card.

> **Exception:** For a small, one-off project with a vendor you will never use again, companies sometimes combine both into a single **Standalone Services Agreement**—putting the legal clauses and the project scope into one document.




## SAP Ariba in simple terms

**SAP Ariba is a corporate purchasing and supplier-management platform.** Think of it as:

> **An internal shopping portal + approval system + purchase-order system + supplier portal + invoice-matching system.**

It helps a company control:

- What employees purchase
- Which suppliers they use
- Who must approve the purchase
- Whether the purchase follows a contract
- Whether goods or services were actually received
- Whether the supplier’s invoice should be paid

Ariba can cover the broader **source-to-pay** process, from selecting suppliers and negotiating contracts through ordering, receiving, invoicing, and payment processing. 

---

# Typical end-to-end process

```text
Business need
    ↓
Purchase requisition
    ↓
Approvals
    ↓
Sourcing and contract, if required
    ↓
Purchase order
    ↓
Supplier delivers goods or performs services
    ↓
Goods receipt or service entry sheet
    ↓
Supplier invoice
    ↓
Invoice matching and reconciliation
    ↓
ERP payment
```

## 1. Employee identifies a need

An employee might need:

- A laptop
- Software licenses
- Cloud services
- A consulting company
- Temporary IT workers
- Cybersecurity testing
- Office equipment

The employee opens **Ariba Guided Buying** and either:

- Selects an item from an approved catalog
- Opens a supplier’s punch-out catalog
- Creates a non-catalog request
- Requests a service with a description or statement of work

This creates a **purchase requisition**, usually called a **PR**. 

## 2. The requisition goes through approvals

Ariba routes the PR to the appropriate approvers based on the company’s configuration. Approval rules can be based on value, category, supplier, cost center or whether the item is non-catalog. 

For example, a software purchase might require approval from:

1. Requester’s manager
2. Cost-center or budget owner
3. IT department
4. Information security
5. Data privacy team
6. Procurement
7. Legal department
8. Finance

A $500 monitor might need only manager approval, while a $500,000 software contract may require all the approvals above.

---

## 3. Procurement performs sourcing, if necessary

If there is no existing approved supplier or contract, the procurement team may run a sourcing event:

- **RFI:** Request for information
- **RFQ:** Request for quotation
- **RFP:** Request for proposal
- Supplier bidding or auction
- Commercial negotiation
- Supplier qualification and risk review

Procurement compares suppliers based on price, technical capability, security, contractual terms, service levels and other criteria. The selected supplier may then be placed under a contract in **SAP Ariba Contracts**. 

Small or routine catalog purchases normally skip this stage because the supplier and prices have already been negotiated.

---

## 4. Ariba creates a purchase order

After the PR is fully approved, Ariba creates one or more **purchase orders**, or POs.

The difference is:

- **PR:** Internal request asking permission to purchase
- **PO:** Formal order sent to the supplier

The supplier receives the PO through **SAP Business Network** and can confirm whether it accepts the order. 

---

# How goods procurement works

For a physical item such as a laptop:

1. Employee selects the laptop from a catalog.
2. Employee submits a PR.
3. Manager and budget owner approve it.
4. Ariba generates a PO.
5. Supplier confirms and ships the laptop.
6. Employee or receiving department records a **goods receipt**.
7. Supplier submits an invoice.
8. Ariba compares the PO, goods receipt and invoice.
9. Approved payment information goes to the ERP system.

This is commonly called a **three-way match**:

```text
Purchase order
      +
Goods receipt
      +
Supplier invoice
```

If the PO says 10 laptops at $1,000 each, but the invoice says 12 laptops at $1,100 each, Ariba creates an exception for review. 

---

# How services procurement works

Services are different because there may be no physical item to receive. Instead, the company must confirm that work was performed.

Examples include:

- IT consulting
- Application development
- Cloud migration
- Penetration testing
- Managed services
- Web design
- Implementation and deployment services

## Typical service workflow

### 1. Create a service requisition

The requester enters information such as:

- Description of the work
- Statement of work, or SOW
- Start and end dates
- Hourly or daily rates
- Estimated hours
- Fixed price
- Deliverables
- Payment milestones
- Maximum budget

### 2. Approve and create a service PO

Once approved, Ariba creates a **service purchase order** and sends it to the supplier.

### 3. Supplier performs the work

The supplier completes the agreed work—for example, completing the first phase of a cloud migration.

### 4. Create a Service Entry Sheet

The supplier or buyer creates a **Service Entry Sheet**, or **SES**, documenting the service performed.

An SES might say:

```text
Milestone: Cloud assessment completed
Amount: $25,000
Completion date: October 15
PO reference: PO123456
```

### 5. Service owner approves the SES

The project manager or service owner verifies that the work was completed and accepts or rejects the SES.

### 6. Supplier submits an invoice

The supplier invoices against the approved service entry sheet or milestone. Ariba checks the invoice against the PO, contract and approved SES before approving it for payment. 

---

# Example: IT consulting project

Suppose an IT company wants a vendor to implement a data platform for **$200,000**.

### The process could look like this:

1. The IT manager creates a request in Ariba.
2. The manager attaches the SOW and supplier proposal.
3. Information security reviews the proposed architecture.
4. Legal reviews intellectual-property, confidentiality and liability terms.
5. Procurement negotiates the price and contract.
6. Finance confirms that the project has budget.
7. The request is approved.
8. Ariba creates a $200,000 service PO.
9. The supplier completes milestone 1.
10. The supplier submits a $50,000 SES for that milestone.
11. The IT project manager approves the SES.
12. The supplier submits a $50,000 invoice.
13. Ariba matches the invoice to the PO and SES.
14. The company’s ERP or accounts-payable system pays the supplier.

The PO could contain multiple milestones:

| Milestone | Amount |
|---|---:|
| Architecture completed | $25,000 |
| Development completed | $75,000 |
| Testing completed | $50,000 |
| Production deployment | $50,000 |

---

# How IT companies typically use Ariba

| Purchase type | Typical Ariba process |
|---|---|
| Laptops, monitors and accessories | Catalog request → approval → PO → goods receipt → invoice |
| Software licenses | Request → security/legal review → contract → PO → invoice |
| SaaS subscriptions | Subscription request → privacy/security review → contract → recurring PO/invoices |
| IT consulting | SOW → approval → service PO → SES/milestone approval → invoice |
| Cloud services | Contract or consumption-based PO → usage/invoice validation |
| Temporary IT workers | Often SAP Fieldglass integrated with Ariba |
| Office or facility supplies | Catalog purchase → PO → receipt → invoice |
| Training and certifications | Non-catalog service request → approval → PO/invoice |

For contingent workers and larger SOW engagements, organizations may use **SAP Fieldglass** for worker, time-sheet and milestone management while integrating the resulting requisition, PO, service confirmation and invoice information with Ariba and the ERP system. 

---

# Does Ariba actually pay the supplier?

Usually, **Ariba validates and approves the invoice, but the company’s ERP or financial system executes the payment**.

For example:

```text
Ariba:
Purchase request → approval → PO → receipt/SES → invoice approval

SAP S/4HANA or another ERP:
Accounting entry → scheduled payment → bank payment
```

After invoice reconciliation, Ariba can send a payment request to the ERP. The ERP processes the payment and can send remittance or payment status back to Ariba. 

---

# Main business purpose

IT companies use Ariba primarily to obtain:

- **Budget control:** Purchases are approved before commitment.
- **Contract compliance:** Employees use negotiated suppliers and pricing.
- **Security and legal review:** Software and service purchases can be routed to specialized teams.
- **Auditability:** The PR, approval, PO, receipt, invoice and payment status are connected.
- **Supplier collaboration:** Suppliers receive orders and submit invoices electronically.
- **Spend visibility:** Management can see which departments and suppliers are receiving company spend.
- **Separation of duties:** The requester, approver, receiver and invoice processor can be different people.

The exact process varies significantly by company. Ariba provides the workflow, but each organization configures its own approval limits, procurement policies, required documents, receiving rules and ERP integrations.



SAP Ariba is a cloud procurement platform that moves a purchase from "we need something" through to "supplier is paid," with a shared network connecting buyers and suppliers. Services and goods follow the same backbone but differ in a few important ways.

**The core flow (source-to-pay)**

1. **Requisition.** An employee or project manager raises a purchase requisition describing what's needed, the cost center or project code, and the estimated amount. Approval routing is rule-based: amount thresholds, category, department, and sometimes a legal or security review for certain spend types.
2. **Sourcing.** For larger or new spend, procurement runs an RFI, RFP, or reverse auction in Ariba Sourcing. Suppliers are invited, submit bids online, and the team scores them on price, technical fit, and risk. For routine buys from existing vendors this step is skipped.
3. **Contract.** The winning terms are captured in Ariba Contracts (rates, SLAs, term, renewal, liability clauses), which then governs later purchases.
4. **Purchase order.** Approved requisitions convert to POs, which are sent to the supplier through the Ariba Network. Many companies also use catalogs, so common items are bought from pre-negotiated lists with no sourcing event.
5. **Receipt.** For goods, this is a goods receipt. For services, it's a **service entry sheet** (timesheet or milestone confirmation) that the business owner approves.
6. **Invoicing and payment.** The supplier submits an invoice through the network, and Ariba matches it against the PO and receipt (the "three-way match"). Matches flow to payment; exceptions go to a queue for resolution. Payment typically runs through the company's ERP, often SAP S/4HANA, though Ariba integrates with Oracle and others too.

**What's different for services**

- Services are rarely bought by quantity, so POs often use a not-to-exceed value, blanket structure, or milestone schedule instead of line-item quantities.
- Many companies use **Statement of Work (SOW) or service-based POs**, with a contract tied to deliverables and rates.
- Receiving is done by approving timesheets or milestones, not confirming a delivery.
- For contingent labor (contractors, staffing), Ariba's **Fieldglass** module handles worker requisitions, onboarding, timesheets, and rate cards. It's separate from core Ariba but often rolled out alongside it.
- Supplier onboarding and risk checks (security questionnaires, insurance, compliance) carry more weight, since service vendors often access systems or data.

**How IT companies typically use it**

- **Software and SaaS licensing:** Renewals tracked in contracts, with negotiation events run before the renewal date to get leverage.
- **Cloud and infrastructure:** Often managed through master agreements, with invoices matched against usage reports, sometimes supported by FinOps tooling outside Ariba.
- **Contract labor and consulting:** Fieldglass for staff augmentation; SOW-based POs for project work with system integrators and consultancies.
- **Hardware and equipment:** Catalog buying for laptops, monitors, and peripherals from approved vendors such as Dell or Lenovo.
- **Vendor governance:** Supplier registration, performance scorecards, and risk monitoring, so only approved vendors get POs.
- **Spend visibility:** Analytics on category and vendor spend, plus compliance checks (e.g., buying outside contract).

**Practical notes**

- Many IT companies use only part of Ariba, such as just Buying and Invoicing plus the Network, and handle sourcing in email or other tools.
- A common pain point is *PO-after-the-fact*: teams engage a vendor first and raise the PO later, which breaks the three-way match. Most procurement policies push hard against this.
- Configuration varies a lot between companies, so exact screens, approval steps, and terminology (e.g., "SES" versus "timesheet") depend on how your organization's administrators have set it up.

If you tell me whether you're on the buyer side (raising requisitions), the supplier side (invoicing through the Network), or evaluating Ariba for adoption, I can go deeper into that role's day-to-day steps.

Source-to-Pay (S2P) is the whole lifecycle, and Source-to-Contract (S2C) and Procure-to-Pay (P2P) are its two halves. The split happens at the signed contract. Everything before it is "upstream," everything after is "downstream."

```
SOURCE-TO-PAY (S2P)
┌─────────────────────────────────┬──────────────────────────────────┐
│ UPSTREAM: Source-to-Contract    │ DOWNSTREAM: Procure-to-Pay       │
│ (S2C)                           │ (P2P)                            │
│                                 │                                  │
│ Spend analysis → Sourcing event │ Requisition → PO → Receipt →     │
│ → Negotiation → Award →         │ Invoice → Match → Payment        │
│ Contract signed                 │                                  │
└───────────────┬─────────────────┴──────────────────┬───────────────┘
                └──── the contract is the handoff ───┘
```

**Upstream: Source-to-Contract (strategic)**

This is where procurement decides *who* to buy from and on *what terms*. It's done occasionally per category or supplier, not for every purchase.

- **Spend analysis:** Look at what the company spends, with whom, and where consolidation could save money.
- **Supplier discovery and qualification:** Find candidates, check financial, security, and compliance risk.
- **Sourcing events:** RFI, RFP, RFQ, or reverse auctions to compare bids.
- **Negotiation and award:** Select the supplier and agree on rates, SLAs, term, and liability.
- **Contract authoring and signature:** Capture the terms in a contract repository, with renewal dates and obligations tracked.

In Ariba these map to modules like Sourcing, Contracts, Supplier Lifecycle and Performance (SLP), and Supplier Risk.

**Downstream: Procure-to-Pay (transactional)**

This is the day-to-day execution of buying under the agreed terms. It runs constantly, with high volume.

- **Requisition and approval:** An employee asks to buy something.
- **Purchase order:** Issued to the supplier, ideally referencing the contract so the negotiated rates apply.
- **Receiving:** Goods receipt, or service entry sheet/timesheet approval for services.
- **Invoice and matching:** Supplier invoices, matched to PO and receipt.
- **Payment:** Released through the ERP.

In Ariba these map to Buying and Invoicing, the Ariba Network, and catalogs.

**How they connect**

- **The contract is the bridge.** S2C produces it; P2P consumes it. A PO should pull its prices, terms, and supplier from an existing contract, which is what "buying on contract" means.
- **Data flows back upstream.** P2P generates actual spend data, which feeds the next round of spend analysis and shows where people are buying off-contract (called *maverick* or *tail spend*). That tells sourcing what to renegotiate or consolidate.
- **Compliance depends on both.** A great contract saves nothing if employees bypass it, and a smooth P2P process buys at bad rates if the sourcing was weak.

**Why companies often treat them separately**

- Different owners: S2C is run by category managers and strategic sourcing. P2P is run by procurement operations, accounts payable, and end users.
- Different cadence: S2C events happen per category, maybe yearly or at contract renewal. P2P happens daily.
- Different rollout: Many companies adopt P2P first (to control purchasing and invoicing), then add S2C later. Others do the reverse. This is why the earlier note about IT companies using only part of Ariba is common.

**An IT example**

Say a company needs a managed security services provider. Upstream, procurement issues an RFP, scores three vendors, negotiates, and signs a 3-year master agreement with an hourly rate card. Downstream, a security manager raises a requisition each quarter for the work, a PO is issued against that contract, the manager approves the monthly service entry sheets, and Ariba matches the vendor's invoices before payment. The spend then feeds back into the next renewal negotiation.
