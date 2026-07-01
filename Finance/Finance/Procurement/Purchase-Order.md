Purchase Order — D365 Finance & Operations

D365FO-KnowledgeBase / Finance / Procurement


1. Overview

The Purchase Order module in D365FO manages the procurement lifecycle — from purchase requisition and vendor quotation through order placement, goods receipt, and vendor invoicing.

Navigation: Procurement and Sourcing > Purchase Orders > All Purchase Orders


2. Key Concepts

ConceptDescriptionPurchase RequisitionInternal request to purchase goods/servicesRequest for Quotation (RFQ)Sent to vendors to obtain pricingPurchase Order (PO)Confirmed order placed with a vendorProduct ReceiptConfirms goods received (updates inventory)Vendor InvoiceFinancial document posted to Accounts PayableThree-Way MatchMatching PO, Product Receipt, and Invoice before payment


3. End-to-End Process

Purchase Requisition (optional)
      ↓
Request for Quotation (optional)
      ↓
Purchase Order Created
      ↓
PO Confirmation Sent to Vendor
      ↓
Goods Received (Product Receipt posted)
      ↓
Vendor Invoice Received & Matched
      ↓
Invoice Approved & Posted to AP
      ↓
Payment Run


4. Creating a Purchase Order


Go to Procurement and Sourcing > Purchase Orders > All Purchase Orders
Click New
Select Vendor Account — address, currency, and payment terms auto-populate
On the Lines tab, add items:

Item number (or procurement category for non-stock)
Quantity
Unit price
Delivery date
Site and Warehouse



Confirm the PO via Purchase > Actions > Confirm



5. Product Receipt (Goods Receipt)

When goods arrive:


Open the PO
Go to Receive > Product Receipt
Enter the Product Receipt number (vendor delivery note reference)
Adjust quantities if partial delivery
Post — inventory is updated and an accrual is created in GL



6. Vendor Invoice Matching

D365FO supports two-way and three-way matching:

Match TypeWhat is ComparedTwo-WayPO price vs Invoice priceThree-WayPO price + Product Receipt quantity vs Invoice

Navigation: Accounts Payable > Invoices > Pending Vendor Invoices

Matching tolerances (%) are configured per vendor or globally in AP parameters.


7. Key Configuration Areas

7.1 Procurement & Sourcing Parameters

Navigation: Procurement and Sourcing > Setup > Procurement and Sourcing Parameters

SettingNotesPurchase order encumbranceEnable for budget controlPrice tolerance %Allowed variance between PO and invoice priceDelivery date controlControls lead time calculation

7.2 Vendor Groups & Posting Profiles

Ensure vendors are assigned to:


Vendor group
Purchase tax group
Posting profile (maps to AP summary account in GL)


7.3 Procurement Categories

Used for non-stock purchases (services, expenses).

Navigation: Procurement and Sourcing > Procurement Categories

7.4 Purchase Agreements

Framework agreements with vendors for blanket orders or committed quantities/amounts.

Navigation: Procurement and Sourcing > Purchase Agreements


8. Posting Overview

ActionInventory ImpactFinancial ImpactPO ConfirmationNoneOptional encumbrance/commitmentProduct ReceiptStock increasedAP accrual debit / Accrued liability creditVendor InvoiceNone (already received)AP accrual reversed + AP balance updated


9. Common Gotchas


Product receipt not posted before invoice: Three-way match will fail. Always ensure product receipt is posted first.
Price tolerance breaches: If the invoice price differs from PO beyond the allowed tolerance, the invoice will go on hold for approval.
Partial deliveries: D365FO handles partial receipts natively — remaining open quantity stays on the PO.
Over-delivery: Controlled by the "Over-delivery" % on the PO line or item default order settings.
Purchase order encumbrance: If budget control is enabled, PO confirmation will check available budget. Insufficient budget = error or warning depending on config.
Currency differences: If PO is in vendor currency, exchange rate differences at invoice time are posted to an FX variance account.



10. Reporting

ReportNavigationPurchase order confirmationsPurchase > Generate > Purchase OrderProduct receipt journalReceive > Journals > Product ReceiptInvoice journalInvoice > Journals > InvoiceOpen purchase ordersProcurement and Sourcing > Inquiries > Orders > Open OrdersVendor agingAccounts Payable > Inquiries > Vendor Aging Report


11. Related Modules


Inventory Management — stock is updated on product receipt
Accounts Payable — vendor invoices and payment runs
Budget Control — PO encumbrances consume budget
Warehouse Management — advanced receiving (if WMS enabled)



12. Open Issues / Notes

#NoteOwner
