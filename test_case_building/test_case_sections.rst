.. _testcase_sections:

******************
Test case sections
******************

    .. image:: pictures/ride_03d_test_case.png

..

An Alyvix test case should be structured in at least 3 different sections: the main section ``<testcase_name>``, the subsections ``setup`` and ``teardown``.

The main section ``<testcase_name>`` is created selecting ``New Test Case`` from the :ref:`suite options <testcase_editing>`.

The subsections ``setup`` and ``teardown`` are created selecting ``New User Keyword`` from the :ref:`suite options <testcase_editing>`. Moreover, they have to be really set as the test *Setup* and *Teardown* sections: click on the button of the suite settings and set them in ``Suite Setup`` and ``Suite Teardown``.


.. _testcase_sections-main_sections-main_body:

Main body
=========

    .. image:: pictures/ride_03e_test_case.png

..

The main body ``<testcase_name>`` is executed after the ``setup`` section and it is a list of :ref:`Alyvix system keywords <system_keywords>`, :ref:`Alyvix visual keywords <visual_keywords>`, `Robot Framework 3.0 syntax <http://robotframework.org/robotframework/latest/libraries/BuiltIn.html>`_, `Python 2.7 methods <https://docs.python.org/2/library/index.html>`_ and subsections (created selecting ``New User Keyword`` from the :ref:`suite options <testcase_editing>`).

.. note::
    It is recommended to subdivide the test case in subsections that are logically isolated.


.. _testcase_sections-main_sections-setup_section:

Setup section
=============

    .. image:: pictures/ride_03f_test_case.png

..

The ``setup`` section codes all the **declarations of performance measures** that are **expected at the test end as its output**.

Typically, a **declared performance measure** corresponds to the name of an :ref:`Alyvix visual keyword <visual_keywords>` ``<keyword_name>``.

The **declaration of a performance measure** should be done properly using the :ref:`Add Perfdata <system_keywords-performance_keywords-add_perfdata>` keyword and setting the :ref:`keyword detection_settings <visual_keywords-detection_settings>` as *Performance* and *Break*.

+-------------------------------------------------------+-----------------------------------------+-----------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *Declaration* in the test                             | *Break* option in the keyword           | *Performance* option in the keyword           | *Description*                                                                                                                                                                                   |
+-------------------------------------------------------+-----------------------------------------+-----------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``Add Perfdata | <keyword_name>``                     | .. image:: pictures/break_checked.png   | .. image:: pictures/performance_checked.png   | **Blocking** transaction, with **latency**: I **do not solve** it, I **break** the test and I report ``CRITICAL``                                                                               |
+-------------------------------------------------------+-----------------------------------------+-----------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``Add Perfdata | <keyword_name> | <timeout_seconds>`` | .. image:: pictures/break_unchecked.png | .. image:: pictures/performance_checked.png   | **Blocking** transaction, with **latency**: I **solve** it, in any case I **continue** the test and I report ``CRITICAL``; ``<timeout_seconds>`` should be bigger than ``<critical_threshold>`` |
+-------------------------------------------------------+-----------------------------------------+-----------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``Add Perfdata | <keyword_name> | 0``                 | .. image:: pictures/break_unchecked.png | .. image:: pictures/performance_checked.png   | **Possible** transaction, with **latency**: I **try to solve** it, in any case I **continue** the test and I report ``OK``; it has to be inserted in the row right before the declared keyword  |
+-------------------------------------------------------+-----------------------------------------+-----------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                                                       | .. image:: pictures/break_checked.png   | .. image:: pictures/performance_unchecked.png | **Blocking** transaction, with **no latency**: I **do not solve** it, I **break** the test; it has not to be insert it as the last keyword                                                      |
+-------------------------------------------------------+-----------------------------------------+-----------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                                                       | .. image:: pictures/break_unchecked.png | .. image:: pictures/performance_unchecked.png | **Possible** transaction, with **no latency**: I **try to solve** it, in any case I **continue** the test                                                                                       |
+-------------------------------------------------------+-----------------------------------------+-----------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. warning::
    Be sure to **do not declare performance measures as follows**, just because they make no sense (e.g. expecting a performance that will not be measure).

+---------------------+-----------------------------------+-----------------------------------------+-----------------------------------------------+------------------------+
|                     | *Declaration* in the test         | *Break* option in the keyword           | *Performance* option in the keyword           | *Description*          |
+---------------------+-----------------------------------+-----------------------------------------+-----------------------------------------------+------------------------+
| **Do not do this!** | ``Add Perfdata | <keyword_name>`` | .. image:: pictures/break_unchecked.png | .. image:: pictures/performance_unchecked.png | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------+-----------------------------------------------+------------------------+
| **Do not do this!** | ``Add Perfdata | <keyword_name>`` | .. image:: pictures/break_checked.png   | .. image:: pictures/performance_unchecked.png | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------+-----------------------------------------------+------------------------+
| **Do not do this!** |                                   | .. image:: pictures/break_unchecked.png | .. image:: pictures/performance_checked.png   | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------+-----------------------------------------------+------------------------+
| **Do not do this!** |                                   | .. image:: pictures/break_checked.png   | .. image:: pictures/performance_checked.png   | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------+-----------------------------------------------+------------------------+


.. _testcase_sections-main_sections-teardown_section:

Teardown section
================

    .. image:: pictures/ride_03g_test_case.png

..

The ``teardown`` section codes the **termination procedures from every possible broken state** of the test case: the test must always (re)start from the same beginning state (e.g. a clean desktop of the probe). For building a proper termination procedure you can :ref:`use visual keywords <visual_keywords>`, :ref:`close windows <system_keywords-window_keywords-close_window>`, :ref:`send shortcuts <system_keywords-io_keywords-send_keys>` and :ref:`kill processes <system_keywords-debug_keywords-kill_process>`.

Finally, you have to :ref:`print the performance Nagios output <system_keywords-performance_keywords-print_perfdata>`.

Eventually, you could :ref:`publish the performance points <system_keywords-performance_keywords-publish_perfdata>`, :ref:`store the test features and the performance measures <system_keywords-performance_keywords-store_perfdata>` and :ref:`store the scraped strings <system_keywords-performance_keywords-store_scrapdata>`.
