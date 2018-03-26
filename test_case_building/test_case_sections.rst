.. _testcase_sections:

******************
Test case sections
******************


.. _testcase_sections-main_sections:

Main sections
=============

    .. image:: pictures/ride_03d_test_case.png

..


.. _testcase_sections-main_sections-main_body:

Main body
---------

    .. image:: pictures/ride_03e_test_case.png

..

main body of a test to code with Alyvix system keywords, Alyvix visual keywords, RobotFramework syntax and Python methods


.. _testcase_sections-main_sections-setup_section:

Setup section
-------------

    .. image:: pictures/ride_03f_test_case.png

..

setup setion of a test to code with performance declarations that are expected at the test end

+-------------------------------------------------------+-----------------------------------------------+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| *Declaration* in the test                             | *Performance* option in the keyword           | *Break* option in the keyword           | *Description*                                                                                                                                                                                   |
+-------------------------------------------------------+-----------------------------------------------+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``Add Perfdata | <keyword_name>``                     | .. image:: pictures/performance_checked.png   | .. image:: pictures/break_checked.png   | **Blocking** transaction, with **latency**: I **do not solve** it, I **break** the test and I report ``CRITICAL``                                                                               |
+-------------------------------------------------------+-----------------------------------------------+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``Add Perfdata | <keyword_name> | <timeout_seconds>`` | .. image:: pictures/performance_checked.png   | .. image:: pictures/break_unchecked.png | **Blocking** transaction, with **latency**: I **solve** it, in any case I **continue** the test and I report ``CRITICAL``; ``<timeout_seconds>`` should be bigger than ``<critical_threshold>`` |
+-------------------------------------------------------+-----------------------------------------------+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``Add Perfdata | <keyword_name> | 0``                 | .. image:: pictures/performance_checked.png   | .. image:: pictures/break_unchecked.png | **Possible** transaction, with **latency**: I **try to solve** it, in any case I **continue** the test and I report ``OK``; it has to be inserted in the row right before the declared keyword  |
+-------------------------------------------------------+-----------------------------------------------+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                                                       | .. image:: pictures/performance_unchecked.png | .. image:: pictures/break_checked.png   | **Blocking** transaction, with **no latency**: I **do not solve** it, I **break** the test; it has not to be insert it as the last keyword                                                      |
+-------------------------------------------------------+-----------------------------------------------+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                                                       | .. image:: pictures/performance_unchecked.png | .. image:: pictures/break_unchecked.png | **Blocking** transaction, with **no latency**: I **try to solve** it, in any case I **continue** the test                                                                                       |
+-------------------------------------------------------+-----------------------------------------------+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

+---------------------+-----------------------------------+-----------------------------------------------+-----------------------------------------+------------------------+
|                     | *Declaration* in the test         | *Performance* option in the keyword           | *Break* option in the keyword           | *Description*          |
+---------------------+-----------------------------------+-----------------------------------------------+-----------------------------------------+------------------------+
| **Do not do this!** | ``Add Perfdata | <keyword_name>`` | .. image:: pictures/performance_unchecked.png | .. image:: pictures/break_unchecked.png | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------------+-----------------------------------------+------------------------+
| **Do not do this!** | ``Add Perfdata | <keyword_name>`` | .. image:: pictures/performance_unchecked.png | .. image:: pictures/break_checked.png   | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------------+-----------------------------------------+------------------------+
| **Do not do this!** |                                   | .. image:: pictures/performance_checked.png   | .. image:: pictures/break_unchecked.png | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------------+-----------------------------------------+------------------------+
| **Do not do this!** |                                   | .. image:: pictures/performance_checked.png   | .. image:: pictures/break_checked.png   | **It makes no sense!** |
+---------------------+-----------------------------------+-----------------------------------------------+-----------------------------------------+------------------------+


.. _testcase_sections-main_sections-teardown_section:

Teardown section
----------------

    .. image:: pictures/ride_03g_test_case.png

..

teardown setion of a test to code with termination procedures from every possible test states, system keywords for printing, saving, publishing of performance points
