.. _alyvix_2-5-3_release_notes:

**************************
Alyvix 2.5.3 release notes
**************************


Alyvix 2.5.3 was released on December 18, 2017.

Python 2.7.14 64bit official distribution is now the recommended Python version to power Alyvix.


.. _alyvix_2-5-3_release_notes_new_features:

============
New Features
============


.. _alyvix_2-5-3_release_notes_pip_install:

Pip Install
-----------

You can install Alyvix through :ref:`pip<install>`.

.. warning::
    From the next release, ``pip`` will be the only package manager for Alyvix.

For now, you can still install Alyvix 2.5.3 through :ref:`conda<install_with_internet>`.


.. _alyvix_2-5-3_release_notes_improvements:

============
Improvements
============

    * graphic definition screen for :ref:`Object Finder<visual_keywords-object_finder>` and :ref:`Scraper<visual_keywords-text_scraper>`
    * a unique ``run_code`` field, publishing the performance data through :ref:`NATS<system_keywords-performance_keywords-publish_perfdata-nats_mode>`, at each new test case execution


.. _alyvix_2-5-3_release_notes_bug_fixing:

=========
Bug fixes
=========

    * building maintenance of the Alyvix conda package for supporting ``conda`` install, **one last time**
    * sanity check for :ref:`keyword naming<visual_keywords-name_components>`
    * cancel :ref:`Finder<visual_keywords-image_finder>` operations pressing :kbd:`ESC`
    * unlimited :ref:`ROI<visual_keywords-keyword_definition>` fix for :ref:`Finder<visual_keywords-image_finder>`
    * sanity check for :ref:`ROI<visual_keywords-keyword_definition>` selections
    * add :ref:`Text Finder<visual_keywords-text_finder>` as :ref:`Object Finder<visual_keywords-object_finder>` subcomponent
    * retain the encryption option of :ref:`Image Finder<visual_keywords-image_finder>`
    * delete Alyvix keywords pressing :kbd:`CTRL+D` in the :ref:`keyword selector<visual_keywords-keyword_definition>`
    * publish rename and sum performance through :ref:`NATS<system_keywords-performance_keywords-publish_perfdata-nats_mode>`
    * cumulant performance fix publishing data through :ref:`NATS<system_keywords-performance_keywords-publish_perfdata-nats_mode>`
    * retain keyword tags and fields publishing data through :ref:`NATS<system_keywords-performance_keywords-publish_perfdata-nats_mode>`
