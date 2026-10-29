# Project Overview

Status: **Design stage.** DineFlow is the Restaurant Service System described in the source materials. The repository specifies intended behavior; it contains no implemented application.

## Problem and product goals

Customers need to know where they can eat, reserve a suitable table, and plan dishes before arrival. During a visit, finding a waiter and settling the bill can add avoidable waiting. Restaurant staff need a consistent view of reservations, pre-orders, and customer requests.

DineFlow aims to connect these activities through a smartphone-accessible customer experience and restaurant staff workflows. It can communicate a requested arrival and food-ready time; whether the restaurant can guarantee that time remains a business/integration decision, not a promise established by the model.

## Roles and responsibilities

| Role | Goal | Recorded scope | Proposed allocation requiring validation |
| --- | --- | --- | --- |
| Customer | Plan a visit and obtain service | Search/filter restaurants, view information, floor plans and menus, book, pre-order, prepay, call a waiter, and pay the bill | Ownership checks for access to personal bookings/orders; identity mechanism TBD |
| Waiter | Respond to in-restaurant requests | Receive waiter-call notifications as restaurant staff (FR-014) | Acknowledge and resolve assigned calls; read relevant pre-orders for the assigned restaurant |
| Manager | Coordinate restaurant operations | Restaurant staff collectively manage reservations and pre-orders (FR-012–FR-013) | Manage restaurant-scoped reservations, pre-orders, and availability; menu editing only if explicitly agreed |

The division between Waiter and Manager is proposal **P-STAFF**, not an approved permission model. These are independently assignable roles: one employee may hold both in one restaurant and a different role set elsewhere. Holding WAITER never automatically grants MANAGER. Authentication and authorization for restaurant management are already required by NFR-006. See the [permission matrix](requirements/functional-requirements.md#proposed-staff-permissions).

Payment providers and restaurant/POS systems are external collaborators. They are not subclasses of users or internal domain objects.

## Main business workflows

1. **Discover and book:** search and filter restaurants; inspect restaurant information, floor plan, and time-based availability; select a table/time; create a reservation or receive an explicit conflict. Displayed availability is a preview, not a booking guarantee.
2. **Pre-order and prepay:** associate a draft pre-order with a reservation, choose dishes and quantities, and review a quoted amount. The customer can confirm, cancel, or leave before initiating payment. Show confirmed success, failure, or an unresolved payment outcome accurately; deliver confirmed information to the restaurant.
3. **Receive service:** a customer at a restaurant calls a waiter; DineFlow routes the notification to relevant restaurant staff. Acknowledgement, resolution, and delivery-failure handling are proposed workflow details.
4. **Pay the bill:** allow an in-restaurant customer to pay the restaurant bill by phone. The source of the bill, adjustments, and reconciliation with the POS remain TBD; this is distinct from prepayment for a pre-order.
5. **Improve later visits:** recorded activity can support preference profiles and recommendations (Should Have). Average occupancy, dish advice, additional in-restaurant ordering, favorites, and ratings retain their Could Have priority.

Detailed flows and alternatives are specified in [use cases](requirements/use-cases.md). Proposed states are defined once in the [functional requirements](requirements/functional-requirements.md#proposed-lifecycle-model).

## Product boundaries

DineFlow handles customer interactions, reservation/order coordination, staff-facing access, and integration status. The restaurant remains responsible for physical seating, food preparation, and service. The system does not currently specify inventory procurement, payroll, kitchen production scheduling, or guarantees about dish acceptance.

AC-001 and AC-005 require restaurant-side integration capability and information exchange. They do not decide whether DineFlow or the POS owns reservation availability. AC-002 recommends external card processing; the diagrams adopt it as a proposed solution. Provider and POS selection, authoritative booking ownership, delivery guarantees, and failure recovery remain open.

Cancellation, no-shows, refund eligibility, and refusal of prepared food require agreed policies. They are decision topics rather than approved extra functionality. International expansion was discussed as a possibility; it is not part of the recorded release requirements.

## Release scope and project scale

The recorded Must Have requirements form the candidate MVP baseline, including staff operations, waiter calls, prepayment, and bill payment. A smaller prototype can simulate external systems, but this does not remove Must Have requirements from the intended release. Should Have and Could Have capabilities remain later candidates subject to planning; they have not been reprioritized. Blacklist management remains excluded from the initial release (FR-027).

## Target businesses and planning scale

The proposed initial audience is **table-service restaurants** that accept reservations, prepare pre-orders, and employ staff who respond to customer calls. This can include independent restaurants and table-service branches of small chains. Each restaurant remains a separate business context under AC-004; chain-wide administration is not established.

Counter-service fast food, including a McDonald's-style workflow, is not the primary example: its usual ordering/service model does not explain DineFlow's reservation and waiter-call requirements. Supporting such businesses would be a future adaptation, not a reason to remove FR-010/FR-014.

**P-SCALE is an illustrative planning envelope, not a forecast, proven capacity, approved requirement, or performance commitment.** Stakeholders must validate or replace it before release planning and load-test acceptance.

| Dimension | Illustrative pilot assumption | Validation needed |
| --- | --- | --- |
| Geography | One region in one country; actual region/country TBD | Initial service area and restaurant operating times |
| Businesses | About 20 table-service restaurants, independent businesses and/or small-chain branches | Restaurant count, grouping, and onboarding variation |
| Tables | About 30 tables per restaurant; approximately 600 total | Real floor plans, capacities, and turnover |
| Customer population | About 2,000 customer accounts | Active-customer and retention estimates |
| Concurrent use | 100 active customer sessions plus 40 staff sessions across the platform | Session activity, device/connectivity mix, and peak pattern |
| Daily volume | About 500 reservation requests and 300 pre-order creations per day | Accepted/rejected mix, cancellations, and per-restaurant distribution |
| Peak write workload | Short test bursts of 2 reservation requests/second and 2 pre-order creations/second across the platform | Burst duration and mix; proposed test burst is one minute, not a sustained-demand estimate |

Accounts, concurrent sessions, daily requests, and requests per second are different dimensions. One active session does not imply one request every second. Conflict-heavy tests must also send simultaneous requests to the same table, independently of aggregate traffic. Search/menu traffic and payment/call rates remain TBD rather than being inferred from registration counts.

International expansion, including China as an instructor's example, is an unapproved future scenario. Its software consequences are discussed in the [architecture expansion assessment](architecture/README.md#geographical-expansion-assessment). Business partner acquisition is distinct from architectural capacity.
