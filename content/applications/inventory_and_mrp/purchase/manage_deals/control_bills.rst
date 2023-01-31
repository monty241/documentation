=====================
Bill Control Policies
=====================

In Odoo, the **Bill Control** policy determines the quantities billed by vendors on every purchase
order, for ordered or received quantities. The policy selected in the settings will act as the
default value and will be applied to any new product created.

Configuration
=============

To view the default bill control policy and make changes, go to
:menuselection:`Purchase --> Configuration --> Settings`, and scroll down to the *Invoicing*
section. Here, there are the two *Bill Control* policy options: :guilabel:`Ordered quantities`
and :guilabel:`Received quantities`.

The policy selected will be the default for any new product created. The definition of each policy
is as follows:

- **Ordered quantities**: When *Ordered quantities* is set as the default bill control policy, a
  vendor bill can be created as soon as a purchase order is confirmed. The products and quantities
  in the purchase order are used to generate a draft bill.
- **Received quantities**: When *Received quantities* is set as the default bill control policy, a
  bill can be created only *after* part of the total order has been received. The products and
  quantities *received* are used to generate a draft bill. An error message will appear if creation
  of a vendor bill is attempted without receiving anything.

.. image:: control_bills/bill-control-policy-error-message.png
   :align: center
   :alt: Bill control policy draft bill error message.

.. note::
   If one or two products need a different control policy, the default bill control setting can be
   overridden by going to the :guilabel:`Purchase` tab in a product's template and modifying its
   **Control Policy** field.

Example flow: Ordered quantities
================================

To complete an example workflow using the *Ordered quantities* bill control policy, first go to
:menuselection:`Purchase --> Configuration --> Settings`, scroll down to the *Invoicing* section,
and select :guilabel:`Ordered quantities`. Then, :guilabel:`Save` changes.

In the Purchase app, create a new Request for Quotation. Fill out the information on the quotation,
add products to the invoice lines, and click :guilabel:`Confirm Order`. Then, click
:guilabel:`Create Bill`. Since the policy is set to *Ordered quantities*, the *Draft Bill* can be
confirmed as soon as it is created, without any products actually being received.

Example flow: Received quantities
=================================

To complete an example workflow using the *Received quantities* bill control policy, first go to
:menuselection:`Purchase --> Configuration --> Settings`, scroll down to the *Invoicing* section,
and select :guilabel:`Received quantities`. Then, :guilabel:`Save` changes.

In the Purchase app, create a new Request for Quotation. Fill out the information on the quotation,
add products to the invoice lines, and click :guilabel:`Confirm Order`. Then, click on the
:guilabel:`Receipt smart button`. Set the quantities in the *Done* column to match the quantities
in the *Demand* column, and :guilabel:`Validate`. Then, in the purchase order, click
:guilabel:`Create Bill` and :guilabel:`Confirm`. Since the policy is set to *Received quantities*,
the *Draft Bill* can be confirmed *only* when at least some of the quantities are received.

3-way matching
==============

Activating 3-way matching ensures that vendor bills are only paid once some or all of the products
included in the purchase order have actually been received. To activate it, go to
:menuselection:`Purchase --> Configuration --> Settings`, and scroll down to the **Invoicing**
section. Then, click :guilabel:`3-way matching: purchases, receptions, and bills`.

.. note::
   3-way matching is intended to work with the bill control policy set to *Received quantities*.

Know when to pay vendor bills with 3-way matching
-------------------------------------------------

When 3-way matching is activated, vendor bills will display the :guilabel:`Should Be Paid` field
under the :guilabel:`Other Info` tab. When a new vendor bill is created, the field will be set to
*Yes*, since a bill can't be created until at least some of the products included in a purchase
order have been received.

.. image:: control_bills/vendor-bill-should-be-paid.png
   :align: center
   :alt: Draft bill should be paid field status.

.. note::
   If the total quantity of products from a purchase order has not been received, Odoo only
   includes the products that *have* been received in the draft vendor bill.

*Draft Bills* can be edited to increase the billed quantity, change the price of the products in
the bill, and add additional products to the bill. If this is done, the :guilabel:`Should Be Paid`
field status will be set to *Exception*. This means that Odoo notices the discrepancy, but doesn't
block the changes or display an error message, since there might be a valid reason for making
changes to the draft bill.

Once payment has been registered for a vendor bill and displays the *Paid* banner, the
:guilabel:`Should Be Paid` field status will be set to *No*.

.. tip::
   The :guilabel:`Should Be Paid` status on bills is set automatically by Odoo. However, the status
   can be changed manually by clicking the field's drop-down menu.

View a purchase order's billing status
======================================

When a purchase order is confirmed, its *Billing Status* can be viewed under the
:guilabel:`Other Information` tab on the purchase order form.

.. image:: control_bills/billing-status-nothing-to-bill.png
   :align: center
   :alt: Purchase order billing status.

Below is a list of the different statuses that a *Billing Status* could appear as and when they are
displayed, depending on the bill control policy used.

+--------------------+--------------------------------------------------------------------------+
| **Billing status** |                              **Conditions**                              |
|                    +------------------------------------------------+-------------------------+
|                    |            *On received quantities*            | *On ordered quantities* |
+--------------------+------------------------------------------------+-------------------------+
| *Nothing to Bill*  |       PO confirmed; no products received       |    *(Not applicable)*   |
+--------------------+------------------------------------------------+-------------------------+
| *Waiting Bills*    |  All/some products received; bill not created  |       PO confirmed      |
+--------------------+------------------------------------------------+-------------------------+
| *Fully Billed*     | All/some products received; draft bill created |    Draft bill created   |
+--------------------+------------------------------------------------+-------------------------+
