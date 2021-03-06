.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

.. _pagetoplevelobjects:

Top-Level Objects
^^^^^^^^^^^^^^^^^

These are the Page TSconfig Top-Level Objects (TLOs):

.. ### BEGIN~OF~TABLE ###

.. container:: table-row

   Property
         mod

   Data type
         ->MOD

   Description
         Options for the backend modules.

         *Notice that these options are merged with settings from User TSconfig
         (TLO: mod) which takes precedence.*


.. container:: table-row

   Property
         RTE

   Data type
         ->RTE

   Description
         This defines configuration for the Rich Text Editor.

         Please refer to the :ref:`RTE Page Tsconfig chapter <t3api:transformations-tsconfig>`
         in Core APIs.


.. container:: table-row

   Property
         TCEMAIN

   Data type
         ->TCEMAIN

   Description
         Configuration for the TYPO3 Core Engine (TCEmain).


.. container:: table-row

   Property
         TCEFORM

   Data type
         ->TCEFORM

   Description
         Extra configuration for the form fields rendered by the TCEforms-class
         in general.


.. container:: table-row

   Property
         TSFE

   Data type
         ->TSFE

   Description
         Options for the TSFE frontend object.


.. container:: table-row

   Property
         TCAdefaults.[table name].[field]

   Data type
         string

   Description
         Sets default values for records. The order of default values when
         creating new records in the backend is this:

         1. Value from $GLOBALS['TCA']

         2. Value from User TSconfig (these settings)

         3. Value from Page TSconfig

         4. Value from "defVals" GET variables (see alt\_doc.php)

         5. Value from previous record based on 'useColumnsForDefaultValues'

         However the order for default values used by tcemain.php if a certain
         field is not granted access to for user will be:

         1. Value from $GLOBALS['TCA']

         2. Value from User TSconfig (these settings)

         So these values will be authoritative if the user has no access to the
         field anyway.

         **Example:**

         This sets the default hidden flag for pages to "clear".

         .. code-block:: typoscript

         	TCAdefaults.pages.hidden = 0


.. container:: table-row

   Property
         user

   Data type
         *(whatever)*

   Description
         This is for custom purposes.

         Deprecated, use "tx\_\*" below from extensions


.. container:: table-row

   Property
         tx\_[extension key with no underscore]

   Data type
         *(whatever)*

   Description
         This is reserved space for extensions.


.. ###### END~OF~TABLE ######

[page]
