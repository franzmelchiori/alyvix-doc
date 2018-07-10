.. _testcase_logic:

***************
Test case logic
***************


.. _testcase_editor-variable_definition:

Variable definition
===================


.. _testcase_editor-section_variable:

Section variable
----------------

Set a **section variable name** to use its **value in more than one position** within a **test case section**:

    +-------------------+------------------+-----------------+
    | ``${<var name>}`` | ``Set Variable`` | ``<var value>`` |
    +-------------------+------------------+-----------------+


.. _testcase_editor-section_list:

Section list
------------

Set a **section list name** to use its **values in more than one position** within a **test case section** and eventually in a **loop**:

    +------------------+-----------------+---------------+---------------+---------------+
    | ``@{list name}`` | ``Create List`` | ``<value 1>`` | ``<value 2>`` | ``<value n>`` |
    +------------------+-----------------+---------------+---------------+---------------+


.. _testcase_editor-global_variable:

Global variable
---------------

Set a **global variable name** to use its **value in more than one position** within a **test case**:

    +------------------------+-------------------+-----------------+
    | ``Set Suite Variable`` | ``${<var name>}`` | ``<var value>`` |
    +------------------------+-------------------+-----------------+


.. _testcase_editor-global_list:

Global list
-----------

Set a **global list name** to use its **value in more than one position** within a **test case** and eventually in a **loop**:

    +------------------------+------------------+---------------+---------------+---------------+
    | ``Set Suite Variable`` | ``@{list name}`` | ``<value 1>`` | ``<value 2>`` | ``<value n>`` |
    +------------------------+------------------+---------------+---------------+---------------+


.. _testcase_editor-catenate:

Catenate
--------

Join a number of text strings (e.g. from a list) in a name for setting a **variable name** with **a fixed prefix** and **different suffixes**:

    +-------------------+--------------+----------------+--------------+--------------+
    | ``${<var name>}`` | ``Catenate`` | ``SEPARATOR=`` | ``<part 1>`` | ``<part n>`` |
    +-------------------+--------------+----------------+--------------+--------------+


.. _testcase_editor-conditional_loop:

Conditional and loop
====================


.. _testcase_editor-if_syntax:

IF syntax
---------

Set a **conditional flow** executing a keyword with its arguments just in case the **given condition is satisfied**:

    +--------------------+--------------------------------------+--------------------+-------------------+
    | ``Run Keyword If`` | ``'${<var name>}' == '<var value>'`` | ``<keyword name>`` | ``<keyword arg>`` |
    +--------------------+--------------------------------------+--------------------+-------------------+


.. _testcase_editor-for_syntax:

FOR syntax
----------

Set a **loop** (e.g. looping a list of numbers) for executing the **indented section** that follows until the **given exit condition is satisfied**:

    +----------+------------------------+--------------------------------------+------------------+
    | ``:FOR`` | ``${<index>}``         | ``IN``                               | ``@{list name}`` |
    +----------+------------------------+--------------------------------------+------------------+
    |          | ``${<var name>}``      | ``<key name>``                       | ``${<index>}``   |
    +----------+------------------------+--------------------------------------+------------------+
    |          | ``Exit For Loop If``   | ``'${<var name>}' == '<var value>'`` |                  |
    +----------+------------------------+--------------------------------------+------------------+


.. _testcase_editor-fail_section:

Fail section trigger
--------------------

Trigger the ``fail_section`` of a **test case** (typically in the teardown section) just in case it **fails within its main body**:

    +--------------------+------------------------------+-------------------------+
    | ``${fail_test}``   | ``Set Variable``             | ``${PREV TEST STATUS}`` |
    +--------------------+------------------------------+-------------------------+
    | ``Run Keyword If`` | ``'${fail_test}' == 'FAIL'`` | ``fail_section``        |
    +--------------------+------------------------------+-------------------------+
