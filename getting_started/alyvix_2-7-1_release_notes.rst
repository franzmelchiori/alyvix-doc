.. _alyvix_2-7-1_release_notes:

**************************
Alyvix 2.7.1 release notes
**************************


Alyvix 2.7.1 was released on July 10, 2018.

Python 2.7.15 64bit official distribution is the recommended Python version to power Alyvix.

Alyvix does :ref:`visual synthetic monitoring <home>`. If your machine matches the :ref:`system requirements <system_requirements>` for Alyvix you can :ref:`install <install>` or :ref:`upgrade <upgrade>` it.


.. _alyvix_2-7-1_release_notes_new_features:

============
New Features
============


.. _alyvix_2-7-1_release_notes_autocontour:

Get Dictionary Value
--------------------

:ref:`Get Dictionary Value <system_keywords-io_keywords-get_dictionary_value>` provides a **value** (e.g. a text string) associated with a **dictionary** in a specified **JSON file**.


.. _alyvix_2-7-1_release_notes_bug_fixing:

=========
Bug fixes
=========

    * :ref:`Edge stretching <alyvix_2-6-2_release_notes_edge_stretching>` is disabled in the :ref:`Autocontour mode <alyvix_2-7-0_release_notes_autocontour>`
    * ``CTRL+Z`` and ``CTRL+Y`` shortcuts are disabled in the :ref:`Autocontour mode <alyvix_2-7-0_release_notes_autocontour>`
    * The cross cursor is visible in the :ref:`Interaction Point mode <visual_keywords-interaction_settings>`
    * The :ref:`keyword columns <visual_keywords-keyword_definition>` in the selector are always filled, autoadapted and adaptable
    * Test cases that have been built with previous Alyvix 2.x versions can be properly :ref:`migrated <backup>`, :ref:`edited <visual_keywords-keyword_definition>` and :ref:`executed <commandline_scripting>` with Alyvix 2.7.1
