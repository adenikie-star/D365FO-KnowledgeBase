Accounts Payable — D365 Finance & Operations

D365FO-KnowledgeBase / Finance / Finance


1. Overview

Accounts Payable (AP) in D365FO manages all outgoing payments to vendors — from invoice receipt and approval through payment processing and reconciliation.

Navigation: Accounts Payable > (all sub-menus)


2. Key Concepts

ConceptDescriptionVendor InvoiceDocument received from vendor for goods/servicesInvoice RegisterQuick capture of invoice before approvalInvoice Approval JournalApproves registered invoices for postingInvoice JournalDirect posting of invoices without PO matchingPayment JournalUsed to process vendor paymentsVendor AgingSummary of outstanding AP balances by due dateSettlementProcess of matching payments to invoices


3. Invoice Processing Options

MethodUse CasePO-Matched InvoiceInvoice linked to a Purchase Order (3-way match)Invoice JournalNon-PO invoices (rent, utilities, services)Invoice Register + ApprovalTwo-step process for invoice capture then approvalVendor Invoice AutomationOCR/AI-driven invoice capture (requires add-on)


4. Posting a Non-PO Vendor Invoice


Go to Accounts Payable > Invoices > Invoice Journal
Create a new journal
Add lines:

Vendor account
Invoice date and due date
Amount (credit = liability)
Offset account (expense or asset GL account)
Tax group



Validate and post



5. Payment Run

5.1 Generate Vendor Payment Proposal


Go to Accounts Payable > Payments > Vendor Payment Journal
Create a new journal
Click Lines > Payment Proposal > Create Payment Proposal
Set filters: due date, vendor, payment method
Review proposed payments
Post the payment journal


5.2 Payment Methods

Configure payment methods under:
Accounts Payable > Payment Setup > Methods of Payment

MethodNotesBACS / SEPABank file export for electronic paymentsChequePrinted cheque with cheque numberWire TransferManual or file-based bank transfer


6. Key Configuration Areas

6.1 AP Parameters

Navigation: Accounts Payable > Setup > Accounts Payable Parameters

SettingNotesInvoice matching policyTwo-way or three-way matchPrice tolerance %Allowed price variance vs POPayment proposal date basisInvoice date / Due date / Cash discount date

6.2 Vendor Posting Profiles

Maps vendors (or vendor groups) to the AP summary account in GL.

Navigation: Accounts Payable > Setup > Vendor Posting Profiles

6.3 Terms of Payment

Defines payment due date calculation rules (e.g. Net 30, 2/10 Net 30).

Navigation: Accounts Payable > Payment Setup > Terms of Payment

6.4 Cash Discount Setup

Configure early payment discounts.

Navigation: Accounts Payable > Payment Setup > Cash Discounts


7. AP Aging & Reconciliation

Vendor Aging Report

Navigation: Accounts Payable > Inquiries and Reports > Vendor Aging Report

Use aging buckets (e.g. Current, 1–30, 31–60, 61–90, 90+) to monitor outstanding balances.

AP to GL Reconciliation

Run the Vendor Balance List and compare to the AP summary account in the Trial Balance.

Navigation: Accounts Payable > Inquiries and Reports > Vendor Balance List


8. Common Gotchas


Invoice on hold after matching: Usually caused by price or quantity tolerance breach. Review under Accounts Payable > Invoices > Invoices on Hold.
Duplicate invoice check: D365FO checks for duplicate invoice numbers per vendor. Ensure this is enabled in AP Parameters.
Settlement issues: If a payment doesn't settle against an invoice, check that both are in the same currency and that the vendor account matches.
Prepayments: Vendor prepayments require a separate prepayment journal type and a prepayment posting profile — don't post as a regular payment.
1099 / WHT reporting: If operating in the US or regions with withholding tax requirements, ensure vendor tax configuration is complete before posting invoices.



9. Reporting

ReportNavigationVendor AgingAP > Inquiries and Reports > Vendor AgingVendor Balance ListAP > Inquiries and Reports > Vendor Balance ListInvoice JournalAP > Inquiries > Journals > Invoice JournalPayment JournalAP > Inquiries > Journals > Payment JournalOpen Vendor InvoicesAP > Invoices > Open Vendor Invoices


10. Related Modules


Purchase Order — PO-matched invoices flow into AP
Cash & Bank Management — bank accounts used for payment runs
General Ledger — AP summary accounts reconcile to GL
Tax — sales tax / VAT calculated on vendor invoices



11. Open Issues / Notes

#NoteOwner
