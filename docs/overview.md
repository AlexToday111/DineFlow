# Project Overview

## Background and problems

DineFlow is described in the source as a Restaurant Service System. It addresses long waits, difficulty finding a waiter, slow service, and poor quality.

## Objectives and high-level capabilities

The following description preserves the source vision. Release scope and priority are defined by the [functional requirements](requirements/functional-requirements.md), rather than by this narrative.

It must allow customers to book a table and order dishes for a specific time, with prepayment by bank card or via a payment system. By the time they arrive at the restaurant, everything will be ready.

Bookings can be made using a floor plan showing the layout, table locations, and the current and average occupancy for that day of the week. When selecting dishes for pre-ordering, customers can view a multimedia menu (with varying levels of detail depending on connection speed) and receive advice on choosing dishes.

In addition, it is necessary to provide the option to select a restaurant based on the range of dishes they would like to have for dinner or lunch, price, distance and other parameters.

Inside the restaurant, customers should be able to call a waiter via their phone and pay the bill. The system tracks and logs the customer’s actions and, based on this, creates a preferences profile and suggests where to go and what to eat tomorrow or later in the week.

## Main user roles

- **Customers:** Search for restaurants, plan visits, book tables, pre-order dishes, make payments, and call waiters by smartphone.
- **Waiters:** Receive customer call notifications; their workflows require validation during prototyping.
- **Restaurant managers and other restaurant staff:** Manage reservations, orders, and table availability. Detailed staff functionality remains an open question.

Payment providers and restaurant POS systems appear as external participants in the existing source diagram; specific providers and systems have not been selected.

See the [open questions](requirements/open-questions.md) for unresolved business goals, boundaries, functionality, and quality attributes.
