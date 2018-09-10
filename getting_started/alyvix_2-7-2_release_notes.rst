.. _alyvix_2-7-2_release_notes:

**************************
Alyvix 2.7.2 release notes
**************************


Alyvix 2.7.2 was released on September 10, 2018.

Python 2.7.15 64bit official distribution is the recommended Python version to power Alyvix.

Alyvix does :ref:`visual synthetic monitoring <home>`. If your machine matches the :ref:`system requirements <system_requirements>` for Alyvix you can :ref:`install <install>` or :ref:`upgrade <upgrade>` it.


.. _alyvix_2-7-2_release_notes_new_features:

============
New Features
============


.. _alyvix_2-7-2_release_notes_wait_process_close:

Wait Process Close
------------------

:ref:`Wait Process Close <system_keywords-process_keywords-wait_process_close>` **waits until** an **ongoing process finishes its execution** and returns that time


.. _alyvix_2-7-2_release_notes_improvements:

============
Improvements
============


.. _alyvix_2-7-2_release_notes_ui:

UI
--

    * :ref:`Alyvix Selector <visual_keywords-keyword_definition>` has a **new design** and **context menus**


.. _alyvix_2-7-2_release_notes_ux:

UX
--

    * :ref:`Component selections <visual_keywords-image_definition>` can **adjusts** their **ROIs**
    * :ref:`Component ROIs <visual_keywords-image_definition>` can **adjusts** their **selections**
    * :ref:`Autocontour <visual_keywords-image_definition>` **depends on** the **screen resolution**, its **aspect ratio** and the **component sizes**
    * :ref:`Object Finder <visual_keywords-object_finder>` can **pack** more than one **basic object** from the :ref:`Alyvix Selector <visual_keywords-keyword_definition>`
    * :ref:`Object Finder <visual_keywords-object_finder>` can **add** more than one **basic object** from its **Object Selector**


.. _alyvix_2-7-2_release_notes_bug_fixing:

=========
Bug fixes
=========

    * :ref:`Create Process <system_keywords-process_keywords-create_process>` can handle ``=`` signs in URLs
    * :ref:`Interaction modes <visual_keywords-interaction_settings>` can always be saved and they really take action
    * :ref:`Alyvix Selector <visual_keywords-keyword_definition>` does not show ghost windows
    * :ref:`Alyvix Selector <visual_keywords-keyword_definition>` shows all its columns when it comes up from the taskbar
