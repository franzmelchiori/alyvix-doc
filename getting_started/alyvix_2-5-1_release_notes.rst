.. _alyvix_2-5-1_release_notes:

**************************
Alyvix 2.5.1 release notes
**************************


Alyvix 2.5.1 was released on August 18, 2017.


.. _alyvix_2-5-1_release_notes_new_features:

============
New Features
============


.. _alyvix_2-5-1_release_notes_visual_scraper:

Visual Scraper
--------------

Alyvix is able to **scrap, process and store text strings visually detected from the screen**. It can be useful to retrieve and use information about an application setup (e.g. from its title bars or windows). It can be applied as web scraper too.

    * Text Scraper can be defined and embed in Object Finder to get **Object Scraper**
    * The scraper keywords **returns the scraped text strings**, which are also integrated in the output HTML reports
    * ``Store Scrapdata`` system keywords **stores all the scraped text strings and their timestamps** in a local SQLite database


.. _alyvix_2-5-1_release_notes_nats_integration:

NATS Integration
----------------

The :ref:`NATS mode<system_keywords-performance_keywords-publish_perfdata>` of ``Publish Perfdata`` allows you to flush all the performance data from Alyvix test cases in a specified **remote InfluxDB** (through a **NATS channel** and a **Telegraf collector**).
    * measure entry in the InfluxDB format
    * caching system
    * Add Perfdata Tag
    * Add Perfdata Field
        Add Perfdata Field | <perf_name>/all | <field_name> | <field_value> (e.g. Add Perfdata Field | ax12_home_ready | aos | bla01, Add Perfdata Field | all | id_session | 1)


.. _alyvix_2-5-1_release_notes_improvements:

============
Improvements
============

    * update of the procedure to build Alyvix conda packages: it is now compatible with the latest Anaconda release
    * PyQt4 is part of Alyvix conda package and the dependency with the latest version of Pillow is solved
    * CTRL+C copia keyword nel selector
    * CTRL+V incolla keyword nel RIDE
    * keyword name sanity check for Text Finders
    * Text Finders and Scrapers are not selectable in Object Finders
    * Text Finders and Scrapers are not runnable in test cases (they must be components in Object Finders)
    * detection settings of Object Finder sub components are disabled
    * Add Perfdata option to add the timestamp to a keyword definition
    * keyword name sanity check for Rename Perfdata, Sum Perfdata, Add Perfdata Tag, Add Perfdata Field
    * review of all output messages
    * Alyvix WPM service has a stand alone Windows installer
    * output warning is raised if the Alyvix WPM service is not installed


.. _alyvix_2-5-1_release_notes_bug_fixing:

=========
Bug fixes
=========

    * rerunning an Object Finder with disappeared detection returned a wrong negative calculated performance
    * an interaction point of a sub component in a Text Finders could disable the interaction point of the next sub component
    * the return from an interaction point of a sub component in an Object Finder led to to its main component
