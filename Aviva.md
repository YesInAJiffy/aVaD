

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
