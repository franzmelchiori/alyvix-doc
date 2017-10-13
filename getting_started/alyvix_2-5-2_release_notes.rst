.. _alyvix_2-5-2_release_notes:

**************************
Alyvix 2.5.2 release notes
**************************


Alyvix 2.5.2 was released on October 10, 2017.

5.0.0 is now the Anaconda recommended version to power Alyvix.


.. _alyvix_2-5-2_release_notes_new_features:

============
New Features
============


.. _alyvix_2-5-2_release_notes_new-send-keys:

New Send Keys
-------------

The new ``Send Keys``, both for the :ref:`system keyword<system_keywords-io_keywords-send_keys>` and the :ref:`visual keywords<visual_keywords-interaction_settings>`, allows you to set the duration of every typed key and the delay between them.

Sometimes you need to **press longer and slow down the key typing** to avoid missed or wrong keys. That is the case of applications provided through **RDP or HDX (Citrix) channels**.

    .. image:: pictures\alyvix_release_notes_2-5-2_new-send-keys_slow.gif

    .. image:: pictures\alyvix_release_notes_2-5-2_new-send-keys_fast.gif


.. _alyvix_2-5-2_release_notes_unlimited-roi:

Unlimited ROI
-------------

The **unlimited ROI** for :ref:`visual keywords<visual_keywords-keyword_definition>` allows to define a ROI with an unlimited boundary towards one or more directions.

    .. image:: pictures\alyvix_release_notes_2-5-2_unlimited-roi.gif


.. _alyvix_2-5-2_release_notes_improvements:

============
Improvements
============

    * Alyvix prints **error screenshots** on top of reports **just for transactions without break** option
    * Alyvix can be powered by **Anaconda 5.0.0**, which is the recommended version to avoid :ref:`issues with older versions<install_issues-pywin32_module>`


.. _alyvix_2-5-2_release_notes_bug_fixing:

=========
Bug fixes
=========

    * removing OF or OS caused bad naming of resulting keywords
    * renaming OS did not renamed their keyword names in the database of scraps
    * :ref:`SIP module caused issues<install_issues-sip_module>` installing Alyvix (an error popup rised in RIDE)
    * :ref:`PyWin32 module caused issues<install_issues-pywin32_module>` installing Alyvix (`import win32ui` failed)
