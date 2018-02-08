.. _alyvix_2-5-1_release_notes:

**************************
Alyvix 2.5.1 release notes
**************************


Alyvix 2.5.1 was released on August 18, 2017.


.. _alyvix_2-5-1_release_notes_new_features:

============
New Features
============


.. _alyvix_2-5-1_release_notes_nats_integration:

NATS Integration
----------------

The :ref:`NATS mode<system_keywords-performance_keywords-publish_perfdata-nats_mode>` of ``Publish Perfdata`` allows you to flush all the performance data from Alyvix test cases in a specified **remote InfluxDB** (through a **NATS channel** and a **Telegraf collector**).

    * publishing each transaction performance as a point in InfluxDB
    * caching system of performance points (storing and resending them) in case of failed connections with NATS
    * ``Add Perfdata Tag`` adds a :ref:`custom tag<system_keywords-performance_keywords-add_perfdata_tag>` to a performance point
    * ``Add Perfdata Field`` adds a :ref:`custom field<system_keywords-performance_keywords-add_perfdata_field>` to a performance point

        .. image:: pictures/alyvix_release_notes_2-5-1_nats.png

.. _alyvix_2-5-1_release_notes_visual_scraper:

Visual Scraper
--------------

Alyvix is able to **scrap, process and store text strings visually detected from the screen**. It can be useful to retrieve and use information about an application setup (e.g. from its title bars or windows). It can be applied as web scraper too.

    * :ref:`Text Scraper<visual_keywords-text_scraper>` can be defined and embed in Object Finder to get **Object Scraper**
    * The scraper keywords **returns the scraped text strings**, which are also integrated in the output HTML reports
    * ``Store Scrapdata`` system keywords **stores all the scraped text strings and their timestamps** in a :ref:`local SQLite database <database_structure-store_scrapdata>`

        .. image:: pictures/alyvix_release_notes_2-5-1_scraper.png


.. _alyvix_2-5-1_release_notes_improvements:

============
Improvements
============

    * new build procedure for **Alyvix conda package**: it is now compatible with the latest Anaconda release
    * **PyQt4** is part of Alyvix conda package and the dependency with the latest version of **Pillow** is solved
    * :kbd:`CTRL+C` copies the selected **keyword name** in the Alyvix selector
    * :kbd:`CTRL+V` pastes the copied **keyword name**
    * :kbd:`CTRL+D` removes the selected **keyword** in the Alyvix selector
    * sanity check of keyword names in **Text Finder**
    * **Text Finders and Scrapers** are not selectable in Object Finders as main components
    * **Text Finders and Scrapers** are not runnable in test cases: they must be sub components of Object Finders
    * the **detection settings** of Object Finder sub components are disabled
    * ``Add Perfdata`` option to add the **timestamp** to a keyword definition
    * sanity check for keyword names as arguments of **Rename Perfdata**, **Sum Perfdata**, **Add Perfdata Tag**, **Add Perfdata Field**
    * review of all **output messages**
    * **Alyvix WPM service** has a stand alone Windows installer
    * an **output warning** is raised if the Alyvix WPM service is not installed


.. _alyvix_2-5-1_release_notes_bug_fixing:

=========
Bug fixes
=========

    * rerunning an **Object Finder** with **disappeared detection** returned a wrong negative calculated performance
    * an **interaction point** of a sub component in a **Text Finders** could disable the interaction point of the next sub component
    * the return from an **interaction point** of a sub component in an **Object Finder** led to to its main component
