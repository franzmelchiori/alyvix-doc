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

Visual scraper
--------------

    * Store Scrapdata


.. _alyvix_2-5-1_release_notes_nats_integration:

NATS Integration
----------------

The new ‘NATS’ type of ‘Publish Perfdata’ allows you to flush all the performance data of Alyvix tests in a specified remote InfluxDB (through Telegraf).
    * one measure with made of..
    * Add Perfdata Tag
    * Add Perfdata Field


.. _alyvix_2-5-1_release_notes_improvements:

============
Improvements
============


.. _alyvix_2-5-1_release_notes_selector_shortcuts:

Selector shortcuts
------------------

    * CTRL+C copia keyword nel selector
    * CTRL+V incolla keyword nel RIDE


.. _alyvix_2-5-1_release_notes_output_message:

Miscellaneous
-------------

    * keyword name sanity check for Text Finders
    * Text Finders and Scrapers are not selectable in Object Finders
    * Text Finders and Scrapers are not runnable in test cases (they must be components in Object Finders)
    * detection settings of Object Finder sub components are disabled
    * keyword name sanity check for Rename Perfdata, Sum Perfdata, Add Perfdata Tag, Add Perfdata Field
    * review of all output messages
    * Alyvix WPM service has a stand alone Windows installer
    * output warning is raised if the Alyvix WPM service is not installed


.. _alyvix_2-5-1_release_notes_bug_fixing:

Bug fixes
---------

    * an interaction point of a sub component in a Text Finders could disable the interaction point of the next sub component
