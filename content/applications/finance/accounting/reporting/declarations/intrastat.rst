=========
Intrastat
=========

Intrastat is the system for data collection and statistical production of goods traded among the
EU Member States. These transactions are:

- Commercial transactions of goods for use, consumption, investment, or resale with ownership
  transfer;
- Goods movements from an EU country to another Member State without transfer of ownership. For
  example, stock relocations or moves of goods before or after outsourced production or processing,
  and after maintenance or repair;
- Returns of goods.

.. seealso::
   - `Eurostat Statistics Explained - Glossary: Intrastat
     <https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:Intrastat>`_

.. note::
   As of **January 1, 2022**, the reporting requirements have changed. One main modification
   concerns the transaction codes that switched to a 2-digits format. All transactions recorded
   after this date must follow the new system’s rules.

Configuration
=============

To enable the Intrastat report, go to :menuselection:`Accounting --> Configuration --> Settings -->
Customer invoices: Intrastat`.

You can now configure the :guilabel:`Default invoice transaction code` and the
:guilabel:`Default refund transaction code` so the :guilabel:`Intrastat` field is automatically
populated when creating a customer invoice or a bill. If you don’t configure these default codes,
you can manually fill in the information.

Generate your Intrastat report
==============================

You can generate the Intrastat report by going to :menuselection:`Accounting --> Reporting --> Audit
reports: Intrastat report`. It is automatically computed based on the information you fill in on the
invoice or bill.

The Intrastat report contains different information: Intrastat codes (Commodity, Region,
Transaction Code, Transport Code), System type, Country, Origin country, Partner VAT, Incoterm
codes, Weight, Supplementary unit, and Value.

You can export your report in XLSX or PDF and then post it to your legal administration.

Intrastat Codes
---------------

The Intrastat report is generated based on four Intrastat Codes. These codes can be viewed by going
to :menuselection:`Accounting --> Configuration --> Invoicing: Intrastat Code`.

Commodity
~~~~~~~~~

Commodity codes are internationally recognized reference numbers that describe a specific product
when importing or exporting goods.

You can fill in the Commodity Code of a product by going to :menuselection:`Accounting --> Customers
--> Products`, open the product you want to edit, and go to the :menuselection:`Accounting tab -->
Intrastat section: Commodity Code.`

.. seealso::
   `Finding commodity codes <https://www.gov.uk/guidance/finding-commodity-codes-for-imports-or-exports>`_

Region
~~~~~~

This code is **only helpful for Belgian companies**. To set the right :guilabel:`Company Intrastat
Region`, go to :menuselection:`Accounting --> Configuration --> Settings --> Customer Invoices:
Intrastat`, and select the right region (Flemish region, Walloon region, Brussels region).

.. Tip::
  If you have multiple warehouses, you can set the :guilabel:`Intrastat region` directly on the
  warehouse by going to :menuselection:`Inventory --> configuration --> Warehouses`. Open the
  wharehouse you want, and add the region.

    .. image:: intrastat/intrastat_region.png
      :align: center
      :alt: Add the region directly to your warehouse

Transaction
~~~~~~~~~~~

Transaction codes consist of two figures describing the transaction's nature. Add the transaction
code in the :guilabel:`Intrastat` column when creating a new invoice or bill. The
:guilabel:`Intrastat` column is not visible by default, click on the columns selection button and
check the Intrastat box to display it.

 .. image:: intrastat/intrastat_column.png
  :align: center
  :alt: Add the region directly to your warehouse

.. important::
   If you created your Odoo database prior to **January 13, 2022**, please :ref:`upgrade
   <general/upgrade>` the ``account_intrastat`` module to add the new transaction codes and
   :ref:`install <general/install>` the ``account_intrastat_expiry`` module to archive the old
   codes.

Transport
~~~~~~~~~

The mode of transport is a one-position numeric code. It represents the active means of transport
with which it is presumed that the goods have left the territory (dispatch) or have entered the
territory (arrival). When you create an invoice or a bill, add the transport code in the
:guilabel:`Other info` tab. First, you must fill in the :guilabel:`Intrastat Country`, and the
:guilabel:`Intrastat Transport Mode` field appears.

System
------

The :guilabel:`System` column contains a system code, based on the type of transaction.

- **19**: The **arrival code** is triggered when you create a vendor bill containing all the
  Intrastat info ;
- **29**: The **dispatch code** is triggered when you issue a Customer invoice containing all the
  Intrastat information.

Country
-------

This column reflects the product's destination country.

Origin country
--------------

This columns corresponds to the country of origin of the product, mentioned on the product page. You
can fill in the :guilabel:`Country of Origin` by going to :menuselection:`Product --> Accounting tab
--> Intrastat section: Commodity Code`.

Partner VAT
-----------

This is your customer's VAT number. The number is identical to the one you state in the :doc:`VIES
declaration <../../taxation/taxes/vat_validation>` for the VAT administration.

Incoterm
--------

Incoterms are 11 internationally recognized rules defining the responsibilities of sellers and
buyers and specify who is responsible for paying for and managing the shipment, insurance,
documentation, customs clearance, and other logistical activities.

You can set the :guilabel:`Default Incoterm` by going to :menuselection:`Accounting -->
Configuration --> Settings --> Customer invoices: Intrastat` so the :guilabel:`Default Incoterm`
field is automatically in the :guilabel:`Other info` tab of your invoice/bill. If you do not fill in
the :guilabel:`Default Incoterm` you can fill it in manually in your invoice/bill.

Weight
------

The :guilabel:`Weight` column is completed based on the :guilabel:`Weight` you indicate in the
product form. To do so, go to :menuselection:`Accounting --> Products`, select the product you want,
and go to the :menuselection:`Accounting` tab --> Intrastat section`. First set the
:guilabel:`Commodity Code`, and then the :guilabel:`Weight` field appears for completion.

Supplementary units
-------------------

For certain commodity codes, you have to specify supplementary units such as m2, m3, pairs, and
litres. For commodity codes that do not require supplementary units, leave this field blank.

You can fill in the :guilabel:`Supplementary Units` by going to :menuselection:`Accounting -->
Products --> Intrastat section`. First set the :guilabel:`Commodity Code`, and then the
:guilabel:`Supplementary Units` field appears for completion.

Value
-----

The value is the invoice value, expressed in euros to a maximum of two decimal places; value always
excludes VAT and excise duty.
