Inventory Management — D365 Finance & Operations

D365FO-KnowledgeBase / Finance / Inventory


1. Overview

Inventory Management in D365FO controls the movement, valuation, and tracking of stock across warehouses and locations. It supports both basic and advanced warehouse operations and integrates tightly with procurement, sales, and production.

Navigation: Inventory Management > (all sub-menus)


2. Key Concepts

ConceptDescriptionItemA product or service tracked in inventoryWarehouseA physical storage location (site > warehouse > location)SiteTop-level inventory dimension — required on all transactionsInventory DimensionsAttributes used to track stock (Site, Warehouse, Location, Batch, Serial)On-hand InventoryCurrent physical stock availableInventory ValuationMethod used to cost stock (FIFO, LIFO, Weighted Average, Standard Cost)Inventory AdjustmentManual correction to stock quantity or valueTransfer OrderMovement of stock between warehouses/sites


3. Inventory Dimension Groups

D365FO uses dimension groups to control how items are tracked.

Storage Dimensions

DimensionRequiredNotesSiteYesAlways mandatoryWarehouseCommonRequired for most itemsLocationOptionalNeeded for WMSPallet IDOptionalAdvanced WMS only

Tracking Dimensions

DimensionUse CaseBatch NumberPerishables, pharmaceuticals, foodSerial NumberHigh-value, warranty-tracked items


4. Costing Methods

MethodDescriptionBest ForFIFOFirst In, First OutPerishables, regulated industriesLIFOLast In, First Out(Limited availability in some regions)Weighted AverageAverage cost across all unitsGeneral manufacturingStandard CostFixed cost set per periodManufacturing, variance analysisMoving AverageReal-time rolling averageDistribution companies


⚠️ Costing method is set at the Item Model Group level and cannot be changed once transactions exist.




5. Key Processes

5.1 Inventory Adjustment


Go to Inventory Management > Journal Entries > Items > Inventory Adjustment
Create a new journal
Add lines with item, site, warehouse, quantity, and cost
Post the journal


5.2 Transfer Orders (Between Warehouses)


Go to Inventory Management > Outbound Orders > Transfer Orders
Create new — specify From/To warehouse
Add item lines and quantities
Ship the transfer order (reduces source)
Receive at destination (increases destination)


5.3 Inventory Counting (Stock Take)


Go to Inventory Management > Journal Entries > Items > Inventory Counting
Create journal and lines (or generate from on-hand)
Enter actual counted quantities
Post — system calculates and posts the variance



6. On-Hand Inquiry

Navigation: Inventory Management > Inquiries and Reports > On-hand List

Key filters to use:


Item number
Site / Warehouse
Batch / Serial number
As of date (for historical view)



7. Key Configuration Areas

7.1 Item Model Groups

Controls costing method, inventory policy, and reservation settings.

Navigation: Inventory Management > Setup > Inventory > Item Model Groups

7.2 Item Groups

Controls the GL posting accounts for inventory transactions (COGS, inventory account, etc.)

Navigation: Inventory Management > Setup > Inventory > Item Groups

7.3 Warehouses

Navigation: Inventory Management > Setup > Inventory Breakdown > Warehouses

Each warehouse must be linked to a Site and can optionally enable WMS (Warehouse Management System).

7.4 Inventory Posting

Maps inventory transaction types to GL accounts.

Navigation: Inventory Management > Setup > Posting > Posting


8. Inventory Closing & Recalculation

D365FO requires a periodic Inventory Close to settle open transactions and calculate final costs.

Navigation: Inventory Management > Periodic Tasks > Closing and Adjustment

TaskFrequencyPurposeInventory RecalculationWeekly/MonthlyInterim cost adjustmentInventory CloseMonthlyFinal settlement of cost transactions


⚠️ Inventory must be closed before the period can be closed in GL. Always run in sequence: Recalculate → Close.




9. Common Gotchas


Negative inventory: Allowed by default if Item Model Group permits — can cause costing issues. Control this in Item Model Groups > "Allow negative physical inventory."
Missing site/warehouse on transactions: Always ensure default order settings are configured per item.
Inventory close errors: Common causes are unposted journals, open transactions, or missing costing data. Review the inventory close log carefully.
Batch/serial number issues: If tracking dimensions are added after transactions exist, migration of existing stock must be carefully planned.



10. Related Modules


Sales Order — consumes inventory via packing slips
Purchase Order — replenishes inventory via product receipts
Production Control — consumes raw materials, produces finished goods
Warehouse Management — advanced location and picking control



11. Open Issues / Notes

#NoteOwner
