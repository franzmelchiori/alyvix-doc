.. _database_structure:

******************
Database structure
******************


.. _database_structure-store_perfdata:

Store Perfdata
==============

At the end of a test case, if you call the :ref:`Store Perfdata <system_keywords-performance_keywords-store_perfdata>` system keyword, you can **store the test case data in a database** setting the folder path and the file name of each database (e.g. ``C:\Python27\Lib\site-packages\`` ``alyvix\robotproxy\`` ``alyvix_testcases\``). The test case databases are made of 4 tables: :ref:`runs <database_structure-runs_table>`, :ref:`sorting <database_structure-sorting_table>`, :ref:`thresholds <database_structure-thresholds_table>`, :ref:`timestamp <database_structure-timestamp_table>`. The SQL databases can be explored with a regular database browser (e.g. DB Browser for SQLite).

  .. image:: pictures/output_database_01.png


.. _database_structure-runs_table:

``runs`` table
--------------

The ``runs`` table contains **one row for every script execution**. In the first column there is the **absolute timestamp** (epoch in seconds) of the **beginning of the script execution**. In the other columns the **transaction performances** are written (milliseconds). In case that a transaction breaks (Alyvix reaches the timeout threshold for that transaction) there will write a ``NULL`` for it and the subsequent ones.

    .. image:: pictures/output_database_02.png


.. _database_structure-sorting_table:

``sorting`` table
-----------------

The ``sorting`` table contains **one row for every script execution**, but just in case that the transaction order or state is changed from the last entry. In the first column there is the **absolute timestamp** (epoch in seconds) at the **beginning of the script execution**. In the other columns the **execution order** for each transaction is written (serial number from ``0``). In case that a transaction breaks there will write a ``-1`` for it and the subsequent ones.

    .. image:: pictures/output_database_03.png


.. _database_structure-thresholds_table:

``thresholds`` table
--------------------

The ``thresholds`` table contains **one row for every script execution**, but just in case the transaction state is changed from the last entry. In the first column there is the **absolute timestamp** (epoch in seconds) of the **beginning of the script execution**. In the other columns the **transaction thresholds** (warning, critical and timeout) are written (milliseconds). In case that a transaction breaks there will write a ``NULL`` for it and the subsequent ones.

    .. image:: pictures/output_database_04.png


.. _database_structure-timestamp_table:

``timestamp`` table
-------------------

The ``timestamp`` table contains **one row for every script execution**. In the first column there is the **absolute timestamp** (epoch in seconds) of the **beginning of the script execution**. In the other columns the **absolute timestamps** (epoch in milliseconds) of the **beginning of each transaction** are written (milliseconds). In case a transaction breaks (Alyvix reaches the timeout threshold for that transaction) there will write a 'NULL' for it and the subsequent ones.

    .. image:: pictures/output_database_05.png


.. _database_structure-store_scrapdata:

Store Scrapdata
===============

At the end of a test case, if you call the :ref:`Store Scrapdata <system_keywords-performance_keywords-store_scrapdata>` system keyword, you can **store the scraped text in a database** setting the folder path and the file name of the database. The test case databases are made of tables, one for each scraper. The SQL databases can be explored with a regular database browser (e.g. DB Browser for SQLite).


.. _database_structure-keyword_name_table:

``<scraper_name>`` table
------------------------

The ``<scraper_name>`` table contains **one row for every script execution**. In the first column ``transaction_timestamp`` there is the **absolute timestamp** (epoch in seconds) of the **beginning of the scraper transaction**. In the second column ``scraped_text`` there is the **raw scraped text from the scraper**.

    .. image:: pictures\output_scrapdatabase_01.png
