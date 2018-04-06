.. _alyvix_2-6-2_release_notes:

**************************
Alyvix 2.6.2 release notes
**************************


Alyvix 2.6.2 was released on March 20, 2018.

Python 2.7.14 64bit official distribution is the recommended Python version to power Alyvix.

Alyvix does :ref:`visual synthetic monitoring <home>`. If your machine matches the :ref:`system requirements <system_requirements>` for Alyvix you can :ref:`install <install>` or :ref:`upgrade <upgrade>` it.


.. _alyvix_2-6-2_release_notes_new_features:

============
New Features
============


.. _alyvix_2-6-2_release_notes_edge_stretching:

Edge Stretching
---------------

You can move and resize :ref:`selections and ROIs <visual_keywords-image_definition>` stretching their edges with the mouse.

    .. image:: pictures/alyvix_release_notes_2-6-2_edge_stretching.gif


.. _alyvix_2-6-2_release_notes_network_analyzer:

Network Analyzer
----------------

You can get the hostname connected through RDP with ``mstsc``.


.. _alyvix_2-6-2_release_notes_scraped_strings:

Scraped Strings
---------------

You can scrap strings for cleaning and mapping them on a set of labels (e.g. AOS name and session ID).
You can sanity check timestamps (e.g. today date, month features, time proximity) from scraped strings.


.. _alyvix_2-6-2_release_notes_improvements:

============
Improvements
============

    * Color detection through a check box in :ref:`Image Finder <visual_keywords-image_finder>` for considering colors in image recognition
    * Available language dictionaries through a combo box in :ref:`Text Finder <visual_keywords-text_finder>` (and :ref:`Scraper <visual_keywords-text_scraper>`)


.. _alyvix_2-6-2_release_notes_bug_fixing:

=========
Bug fixes
=========

    * An alphabet filter for each sub component in :ref:`Text Finder <visual_keywords-text_finder>` (and :ref:`Scraper <visual_keywords-text_scraper>`)
    * :ref:`Show Window <system_keywords-window_keywords-show_window>` does not minimized a maximized window (in background) bringing it in foreground
    * :ref:`Rename Perfdata <system_keywords-performance_keywords-rename_perfdata>` edits the thresholds of renamed keywords
    * Add Perfdata performance points through NATS through :ref:`NATS <system_keywords-performance_keywords-publish_perfdata-nats_mode>`
    * Timedout transactions through :ref:`NATS <system_keywords-performance_keywords-publish_perfdata-nats_mode>` as points with no performance
