# PROJECT_LOG

## Version: v44.5.1
Status: Completed

Resolved
- BUG-001 Happy Hour navigation fixed
- BUG-002 Order detail text color fixed

## Version: v44.6
Status: Completed

Feature:
Benefit Localization

Added:
benefit.* namespace

QA:
Pending

## Version: v44.8
Status: Completed

Feature:
Dough + Size + Crust Localization

QA:
Pending

## Version: v44.9
Status: Completed

Feature:
Topping Localization

QA:
Pending

## Version: v45.0
Status: Completed

Feature:
Side + Drink Localization

QA:
Pending

## Version: v46.0
Status: Completed

Feature:
Cart and Order Review Localization

Added:
cart.*, review.*, orderSummary.*, unit.*, and pizza.* customer-facing localization keys for cart and review flows.

Changed:
Cart and order review rendering now uses existing PJ_I18N translation helpers and menu-name helpers for customer-visible labels, selected option summaries, item quantities, remove actions, and final totals.

QA:
Pending

Notes:
Business logic, price calculations, cart data shape, Firestore order payloads, and screen flow were not changed.

## Version: v46.0.1
Status: Completed

Type:
Hotfix

Issue:
Cart text invisible on white background

Changed:
Scoped Cart and Review text color overrides restore readable typography on white panels without changing order logic, pricing, payloads, Firestore, screen flow, or localization keys.

QA:
Pending

## Version: v47.0
Status: Completed

Changed:
- Review text visibility fix
- Product name display
- Set option cart fix
- Side UX improvement
- Drink quantity UX
- Happy Hour improvement
- Language selection

QA:
Pending

