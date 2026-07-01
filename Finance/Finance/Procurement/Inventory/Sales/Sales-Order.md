Sales Order — D365 Finance & Operations

D365FO-KnowledgeBase / Finance / Sales


1. Overview

The Sales Order module in D365FO manages the end-to-end sales process — from customer quotation through order confirmation, picking, packing, shipment, and invoicing.

Navigation: Sales and Marketing > Sales Orders > All Sales Orders


2. Key Concepts

ConceptDescriptionSales QuotationAn offer sent to a customer before a confirmed orderSales OrderA confirmed commitment to sell goods/services to a customerDelivery ScheduleSplits a single order line into multiple delivery datesPicking ListWarehouse instruction to pick items for an orderPacking SlipConfirms goods have been shipped (updates inventory)Sales InvoiceFinancial document posted to Accounts Receivable


3. End-to-End Process

Customer Request
      ↓
Sales Quotation (optional)
      ↓
Sales Order Created
      ↓
Order Confirmation (printed/sent)
      ↓
Pick & Pack (Warehouse)
      ↓
Packing Slip Posted (inventory reduced)
      ↓
Sales Invoice Posted (AR updated)
      ↓
Payment Received & Settled


4. Creating a Sales Order


Go to Sales and Marketing > Sales Orders > All Sales Orders
Click New
Select Customer Account — address, currency, and payment terms auto-populate
On the Lines tab, add items:

Item number
Quantity
Unit price (pulled from trade agreements or manually entered)
Delivery date



Confirm the order via Sell > Confirm > Order Confirmation



5. Key Configuration Areas

5.1 Sales Parameters

Navigation: Sales and Marketing > Setup > Sales and Marketing Parameters

SettingRecommended ValueNotesDelivery date controlSales lead timeControls ATP/CTP checksPrice searchTrade agreementEnables automatic pricingCredit limit typeBalanceChecks outstanding AR balance

5.2 Number Sequences

Set up number sequences for:


Sales quotations
Sales orders
Packing slips
Sales invoices


5.3 Trade Agreements

Used to set up customer-specific or product-specific pricing.

Navigation: Sales and Marketing > Prices and Discounts > Trade Agreements

5.4 Customer Groups & Posting Profiles

Ensure customers are assigned to the correct:


Customer group
Sales tax group
Posting profile (links to AR summary account in GL)



6. Posting Overview

ActionInventory ImpactFinancial ImpactOrder ConfirmationNoneNone (optional commitment)Packing SlipStock reducedCOGS accrual (optional)InvoiceNone (already reduced)AR debit / Revenue credit


7. Common Configurations & Gotchas


Credit limit holds: If a customer exceeds their credit limit, the order will be placed on hold. Review under Credit and Collections > Credit Limit.
Delivery date mismatches: Always check "Requested ship date" vs "Confirmed ship date" — mismatches cause fulfilment issues.
Trade agreement hierarchy: D365FO applies pricing in a specific priority order — manual price > trade agreement > base price. Ensure trade agreements are activated with the correct journal type.
Intercompany orders: If selling between legal entities, intercompany sales order relationships must be set up under Accounts Receivable > Setup > Intercompany.
Sales tax not calculating: Check that item sales tax group and customer sales tax group are both assigned and that a valid tax code combination exists.



8. Reporting

ReportNavigationSales order confirmationsSell > Generate > Order ConfirmationPacking slip journalSell > Journals > Packing SlipInvoice journalSell > Journals > InvoiceOpen sales ordersSales and Marketing > Inquiries > Orders > Open ordersRevenue by customerGeneral Ledger > Inquiries > Trial Balance (filtered)


9. Related Modules


Inventory Management — stock reservation and picking
Accounts Receivable — invoicing and collections
Warehouse Management — advanced picking and packing (if WMS enabled)
Credit and Collections — credit holds and dunning



10. Open Issues / Notes

#NoteOwner
