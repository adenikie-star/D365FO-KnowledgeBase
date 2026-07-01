Accounts Receivable — D365 Finance & Operations

D365FO-KnowledgeBase / Finance / Finance


1. Overview

Accounts Receivable (AR) in D365FO manages all incoming payments from customers — from sales invoice generation through collections, cash application, and reconciliation.

Navigation: Accounts Receivable > (all sub-menus)


2. Key Concepts

ConceptDescriptionSales InvoiceDocument issued to customer for goods/servicesFree Text InvoiceInvoice not linked to a Sales Order (e.g. rent, services)Customer Payment JournalRecords cash received from customersSettlementMatching a payment to one or more invoicesCredit NoteNegative invoice used to reverse or reduce a chargeCustomer AgingSummary of outstanding AR balances by due dateCollection LettersAutomated dunning notices for overdue invoices


3. Invoice Types

TypeUse CaseSales Order InvoiceGenerated from a confirmed and delivered sales orderFree Text InvoiceDirect AR invoice with no linked sales orderProject InvoiceGenerated from Project Management & Accounting moduleRecurring InvoicePeriodic invoices (subscriptions, retainers)


4. Posting a Free Text Invoice


Go to Accounts Receivable > Invoices > All Free Text Invoices
Click New
Select Customer Account
Enter invoice date, due date, and description
On the Lines tab:

Enter the revenue GL account
Amount
Tax group



Post the invoice



5. Customer Payment Processing

5.1 Posting a Customer Payment


Go to Accounts Receivable > Payments > Customer Payment Journal
Create a new journal
Add payment line:

Customer account
Amount received
Bank account (offset)



Click Settle Transactions to match against open invoices
Post the journal


5.2 Payment Methods

Navigation: Accounts Receivable > Payment Setup > Methods of Payment

MethodNotesBank TransferDirect credit to bank accountDirect DebitSEPA / BACS direct debit schemesChequeCheque received from customerCredit CardRequires payment service integration


6. Collections Management

6.1 Customer Aging

Navigation: Accounts Receivable > Inquiries and Reports > Customer Aging Report

Standard aging buckets: Current, 1–30, 31–60, 61–90, 90+

6.2 Collection Letters (Dunning)

Automated letters sent to customers with overdue balances.

Setup: Accounts Receivable > Setup > Collections > Collection Letter Sequence

LevelTimingToneLevel 17 days overdueFriendly reminderLevel 221 days overdueFormal noticeLevel 345 days overdueFinal demand

Run collection letters: Accounts Receivable > Periodic Tasks > Collection Letters > Print Collection Letters

6.3 Interest Notes

Charge interest on overdue balances.

Navigation: Accounts Receivable > Periodic Tasks > Interest > Create Interest Notes


7. Credit Management

Credit Limit Check

D365FO checks customer credit limits when a sales order is confirmed.

Navigation: Credit and Collections > Setup > Credit Management Parameters

SettingOptionsCredit limit typeNone / Balance / Balance + DeliveriesCredit limit checkWarning / Error / Hold

Credit Holds

Orders exceeding the credit limit are placed on hold.

Release holds: Credit and Collections > Credit Holds > All Credit Holds


8. Key Configuration Areas

8.1 AR Parameters

Navigation: Accounts Receivable > Setup > Accounts Receivable Parameters

SettingNotesSettlement priorityControls which invoices are settled firstAutomatic settlementAuto-match payments to oldest invoicesInterest calculationEnable/disable interest on overdue balances

8.2 Customer Posting Profiles

Maps customer (or customer group) to the AR summary account in GL.

Navigation: Accounts Receivable > Setup > Customer Posting Profiles

8.3 Terms of Payment

Navigation: Accounts Receivable > Payment Setup > Terms of Payment


9. AR to GL Reconciliation

Compare the Customer Balance List to the AR control account in the Trial Balance.

Navigation: Accounts Receivable > Inquiries and Reports > Customer Balance List


10. Common Gotchas


Payment not settling: Check that the customer account, currency, and company match on both the invoice and payment.
Credit limit blocks order but credit is fine: Check if "unposted deliveries" are being included in the balance calculation (AR Parameters).
Collection letters not generating: Verify the collection letter sequence is assigned to the customer and that the minimum balance threshold is exceeded.
Free text invoice tax not calculating: Ensure the customer tax group and item tax group are both populated and a valid combination exists.
Overpayment handling: Use a bridging account or write-off tolerance — don't leave small unmatched credit balances open indefinitely.



11. Reporting

ReportNavigationCustomer AgingAR > Inquiries and Reports > Customer AgingCustomer Balance ListAR > Inquiries and Reports > Customer Balance ListInvoice JournalAR > Inquiries > Journals > Invoice JournalPayment JournalAR > Inquiries > Journals > Payment JournalOpen Customer InvoicesAR > Invoices > Open Customer Invoices


12. Related Modules


Sales Order — sales invoices are generated from sales orders
Cash & Bank Management — receipts post to bank accounts
General Ledger — AR control accounts reconcile to GL
Credit and Collections — credit limits and dunning management



13. Open Issues / Notes

#NoteOwner
