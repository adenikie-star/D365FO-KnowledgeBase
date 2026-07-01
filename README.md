D365FO Knowledge Base

A structured knowledge base for Microsoft Dynamics 365 Finance & Operations — covering functional design templates, module documentation, and implementation guides.


Repository Structure

D365FO-KnowledgeBase/
│
├── README.md                          ← You are here
│
└── Finance/
    ├── Finance/
    │   ├── Accounts-Payable.md        ← Vendor invoices, payments, AP aging
    │   ├── Accounts-Receivable.md     ← Customer invoices, collections, AR aging
    │   └── General-Ledger.md         ← CoA, journals, period close, year-end
    │
    ├── Procurement/
    │   └── Purchase-Order.md         ← PO lifecycle, product receipt, 3-way match
    │
    ├── Inventory/
    │   └── Inventory-Management.md   ← Stock control, costing, transfers, counting
    │
    └── Sales/
        ├── Sales-Order.md            ← Sales lifecycle, trade agreements, invoicing
        └── Templates/
            └── FDD-Template.md       ← Functional Design Document template


Module Documentation

Finance

DocumentDescriptionAccounts PayableVendor invoice processing, payment runs, AP aging, and reconciliationAccounts ReceivableCustomer invoicing, collections, credit management, and cash applicationGeneral LedgerChart of accounts, financial dimensions, period close, and year-end

Procurement

DocumentDescriptionPurchase OrderFull procurement lifecycle from PO creation to vendor invoice and three-way match

Inventory

DocumentDescriptionInventory ManagementStock tracking, costing methods, transfers, adjustments, and inventory close

Sales

DocumentDescriptionSales OrderSales lifecycle from quotation through invoicing, trade agreements, and credit checks


Templates

TemplateDescriptionFDD TemplateStandard Functional Design Document template for D365FO implementation projects


How to Use This Knowledge Base


Finding a topic: Use the table above or GitHub's file search (T key) to navigate to a module.
Creating a new FDD: Copy the FDD Template and fill in the relevant sections for your functional area.
Contributing: Create a branch, add or update the relevant .md file, and raise a pull request for review.



Contributing Guidelines


Use the existing folder structure — place docs in the correct module folder
Follow the standard document format (see existing docs for reference)
Fill in the Open Issues / Notes table at the bottom of each doc with any known gaps
All FDDs should use the standard FDD Template
Keep language clear and functional — this is a practitioner reference, not vendor marketing



Maintainer

NameRoleadenikie-starRepository Owner
