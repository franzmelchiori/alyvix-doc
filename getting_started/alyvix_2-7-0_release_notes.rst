.. _alyvix_2-7-0_release_notes:

**************************
Alyvix 2.7.0 release notes
**************************


Alyvix 2.7.0 was released on July 3, 2018.

Python 2.7.15 64bit official distribution is the recommended Python version to power Alyvix.

Alyvix does :ref:`visual synthetic monitoring <home>`. If your machine matches the :ref:`system requirements <system_requirements>` for Alyvix you can :ref:`install <install>` or :ref:`upgrade <upgrade>` it.


.. _alyvix_2-7-0_release_notes_new_features:

============
New Features
============


.. _alyvix_2-7-0_release_notes_autocontour:

Autocontour
-----------

``RIGHT CLICK`` the mouse to **autocontour components** in all the :ref:`finders <visual_keywords-alyvix_finders>`.

    .. image:: pictures/alyvix_release_notes_2-7-0_autocontour.gif

..

Press ``SPACE`` to **highlight component candidates** in all the :ref:`finders <visual_keywords-alyvix_finders>` and then ``RIGHT CLICK`` the mouse to **autocontour them**.

    .. image:: pictures/alyvix_release_notes_2-7-0_autocontour_highlight.gif


.. _alyvix_2-7-0_release_notes_improvements:

============
Improvements
============


.. _alyvix_2-7-0_release_notes_ux:

UX
--

    * ``RIGHT CLICK`` the mouse on **ROI edges** to **push them to infinity**
    * ``CTRL + LEFT CLICK`` the mouse on a **component SELection** to **reset its ROI**
    * ``CTRL + RIGHT CLICK`` the mouse on a **component SELection** to **remove the component**
    * **Sort and search bars** in the :ref:`keyword selector <visual_keywords-keyword_definition>`
    * ``CTRL + D`` to **remove multiple keywords** in the :ref:`keyword selector <visual_keywords-keyword_definition>`
    * **Remove multiple components** in all the :ref:`finders <visual_keywords-alyvix_finders>`
    * **Autoselect of ROI** for added components in :ref:`OF and OS <visual_keywords-object_finder>` (also after component editing)
    * **Scroll interaction** in all the :ref:`finders <visual_keywords-alyvix_finders>`
    * **Window position** of :ref:`finders <visual_keywords-alyvix_finders>` is **tracked**


.. _alyvix_2-7-0_release_notes_bug_fixing:

=========
Bug fixes
=========

    * :ref:`TF <visual_keywords-text_finder>` to :ref:`TS <visual_keywords-text_scraper>` conversion is fixed
    * :ref:`Object Scraper <visual_keywords-object_scraper>` scraps from the only valid candidate
    * :ref:`Keyword selector <visual_keywords-keyword_definition>` is a regular window: it can be resized and put in background
    * :ref:`Timestamp keywords <system_keywords-timestamp_keywords>` compliant with solar and legal time
