===================
Analytic accounting
===================

:guilabel:`Analytic accounting` helps you track costs and revenues, as well as analyze the
profitability of a project or service. When creating your journal entries, the analytic widget
allows the distribution of cost in one or more analytic accounts.

Configuration
=============

You can enable the :guilabel:`Analytic Accounting` feature by going to :menuselection:`Accounting
--> Configuration --> Settings --> Analytics`.

Analytic accounts
=================

The :guilabel:`Analytic Accounts` give an overview of your costs and revenue.

You can access your existing :guilabel:`Analytic Accounts` by going to :menuselection:`Accounting
--> Configuration --> Analytic Accounting: Analytic Accounts`. To create a new
:guilabel:`Analytic Account`, click :guilabel:`New`, and fill in the required information:

- :guilabel:`Analytic Account`: add the name of your :guilabel:`Analytic Account`;
- :guilabel:`Customer`: select the customer related to your project;
- :guilabel:`Reference`: add a reference to make it easier to find the account when you are on your
  bill;
- :guilabel:`Plan`: an :guilabel:`Analytic Account` must be related to at least one
  :guilabel:`Analytic plan`;
- :guilabel:`Company`: select the company for which the :guilabel:`Analytic Account` will be used;
- :guilabel:`Currency`: select the currency of the :guilabel:`Analytic Account`.

Then, fill in your budget information.

.. seealso::
   :doc:`Financial budget <../adviser/budget>`.

Analytic plans
==============

You can access the :guilabel:`Analytic Plans` by going to :menuselection:`Accounting -->
Configuration --> Analytic Accounting: Analytic Plans`. Click :guilabel:`New` to create a new plan.

.. image:: analytic_accounting/analytic_plans.png
   :align: center
   :alt: create an analytic plan

The following information must be completed:

- :guilabel:`Parent`: link your plan to another :guilabel:`Analytic Plan` to build a hierarchy
  between your plans;
- :guilabel:`Default Applicability`: :guilabel:`Optional`, :guilabel:`Mandatory`, or
  :guilabel:`Unavailable`;
- :guilabel:`Color`: select the color of the tag related to this specific plan;
- :guilabel:`Company`: add the company to which the plan applies;
- :guilabel:`Domain`: choose where your plan is applicable;
- :guilabel:`Financial Accounts Prefix`: select the prefix of the account(s) to which this plan
  should be applied;
- :guilabel:`Product Category`: decide to which product category the plan applies;
- :guilabel:`Applicability`: decide how your plan behaves in the widget when creating a new journal
  entry:

  - :guilabel:`Optional`: if selected, it is not mandatory to add the analytic plan in the widget;
  - :guilabel:`Mandatory`: if selected, an orange bullet is visible in the widget next to the plan
    until the analytic distribution is done (the bullet then turns to green); it is not possible to
    confirm the entry if no analytic account is selected;
  - :guilabel:`Unavailable`: if selected, the plan is not available in the widget.

Two smart buttons are available in the top-right corner:

   - :guilabel:`Subplans`: can be created to have a more complex analytic structure. Click the
     :guilabel:`Subplans` smart button, and then :guilabel:`New` to add a subplan;
   - :guilabel:`Analytic Accounts`: to reach the subplans related to the plan.

.. note::
   - The analytic widget is prefilled based on the :guilabel:`Applicability`, and the
     :ref:`Analytic Distribution Models <analytic_distribution_models>`;
   - Each :guilabel:`Analytic plan` must have at least one :guilabel:`Analytic Account`.

Analytic distribution
=====================

When creating an invoice or a bill it is mandatory to add a plan in the
:guilabel:`Analytic Distribution` column. This opens a **widget**, in which you can fill in the
different information. You can add **tags** to reflect the related :guilabel:`Analytic Accounts`,
and decide how to split the costs between the accounts by modifying the percentage.

.. image:: analytic_accounting/analytic_distribution.png
   :align: center
   :alt: create a distribution template

.. _analytic_distribution_models:

Analytic distribution models
----------------------------

The :guilabel:`Analytic Distribution Models` automatically apply a specific distribution based on
defined criteria.

To create a new :guilabel:`Analytic Distribution Model`, go to :menuselection:`Accounting -->
Configuration --> Analytic Distribution Models`, click :guilabel:`New` and set the conditions your
model has to meet to automatically apply:

- :guilabel:`Partner`: select a partner for which the analytic distribution will be used;
- :guilabel:`Partner Category`: select a partner category for which the analytic distribution will
  be used;
- :guilabel:`Accounts Prefix`: this analytic distribution will apply to all financial accounts
  sharing the prefix specified;
- :guilabel:`Product`: select a product for which the analytic distribution will be used;
- :guilabel:`Product Category`: select a product category for which the analytic distribution will
  be used;
  :guilabel:`Analytic Account` specified in analytic default;
- :guilabel:`Company`: select a company for which the analytic distribution will be used;
- :guilabel:`Analytic Distribution`: if the above conditions are met, the :guilabel:`Analytic plan`
  defined in this field as well as the distribution to be applied between the different analytic
  accounts is selected automatically on the entry.

.. tip::
   To **mass edit** several entries simultaneously, go to :menuselection:`Accounting --> Accounting
   --> Journal items`, and select the ones that need to be updated. Add the required distribution in
   the :guilabel:`Analytic Distribution` column, and click on the :guilabel:`diskette` icon to save.
   The :guilabel:`Analytic distribution template` pops up, and you can save it for later use.
