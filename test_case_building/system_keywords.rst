.. _system_keywords:

***************
System keywords
***************


.. _system_keywords-process_keywords:

Process keywords
================


.. _system_keywords-debug_keywords-create_process:

Create Process
--------------

    +--------------------+-----------------------------------+------------------------------+----+------------------------------+
    | ``Create Process`` | ``<application_executable_path>`` | ``<application_argument_1>`` | .. | ``<application_argument_n>`` |
    +--------------------+-----------------------------------+------------------------------+----+------------------------------+

    * Optional arguments: ``<application_argument_1>``, .., ``<application_argument_n>``.

Example:

    +--------------------+----------------------------------------------------------------------+----------------------------+----------------+
    | ``Create Process`` | ``C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe`` | ``https://www.alyvix.com`` | ``-incognito`` |
    +--------------------+----------------------------------------------------------------------+----------------------------+----------------+

.. warning::
    Type the **application executable path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path_to_folder>\\<application_executable>.exe``).

*Create Process* **runs executable files** (reachable to the given path, e.g. browser application, batch file) **with its optional arguments** (e.g. website address, browser options). This keyword is useful, for example, to run a browser (e.g. Internet Explorer, Chrome) with a website address to point and eventually the option for private browsing.


.. _system_keywords-debug_keywords-kill_process:

Kill Process
------------

    +------------------+---------------------------+
    | ``Kill Process`` | ``<executable_filename>`` |
    +------------------+---------------------------+

Example:

    +------------------+----------------+
    | ``Kill Process`` | ``chrome.exe`` |
    +------------------+----------------+

*Kill Process* **kills a process** of which you provide its executable filename. Have a look at the *Windows Task Manager*, in the *Detail* tab, to know the ongoing programs.

    .. image:: pictures/task_manager.png


.. _system_keywords-window_keywords:

Window keywords
===============


.. _system_keywords-window_keywords-wait_window:

Wait Window
-----------

    +-----------------+---------------------------+-----------------------+-----------------------------+
    | ``Wait Window`` | ``<window_title_regexp>`` | ``timeout=<seconds>`` | ``exception={True, False}`` |
    +-----------------+---------------------------+-----------------------+-----------------------------+

    * Default values: ``timeout=60``, ``exception=True``.

Examples:

    +-----------------+-----------------------------------+
    | ``Wait Window`` | ``synthetic.*monitoring.*alyvix`` |
    +-----------------+-----------------------------------+

    +-----------------+-----------------------------------+----------------+--------------------+
    | ``Wait Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=10`` | ``exception=True`` |
    +-----------------+-----------------------------------+----------------+--------------------+

    +------------------+-----------------+-----------------------------------+---------------+---------------------+
    | ``${wait_time}`` | ``Wait Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=3`` | ``exception=False`` |
    +------------------+-----------------+-----------------------------------+---------------+---------------------+

*Wait Window* **waits until a window runs and is active** in the taskbar. The keyword waits the given **timeout** (an **amount of seconds**) and it waits for a window with a given **title name** (that fits a **regular expression**). When the timeout is expired without having found a window with a proper title, then the test case breaks if the **exception** is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution.

The keyword can return ``${wait_time}``, which is the **amount of seconds** before the keyword has correctly **match the given regular expression** with an ongoing window.


.. _system_keywords-window_keywords-maximize_window:

Maximize Window
---------------

    +---------------------+---------------------------+-----------------------+-----------------------------+
    | ``Maximize Window`` | ``<window_title_regexp>`` | ``timeout=<seconds>`` | ``exception={True, False}`` |
    +---------------------+---------------------------+-----------------------+-----------------------------+

    * Default values: ``timeout=60``, ``exception=True``.

Examples:

    +---------------------+-----------------------------------+
    | ``Maximize Window`` | ``synthetic.*monitoring.*alyvix`` |
    +---------------------+-----------------------------------+

    +---------------------+-----------------------------------+----------------+--------------------+
    | ``Maximize Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=10`` | ``exception=True`` |
    +---------------------+-----------------------------------+----------------+--------------------+

    +------------------+---------------------+-----------------------------------+---------------+---------------------+
    | ``${wait_time}`` | ``Maximize Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=3`` | ``exception=False`` |
    +------------------+---------------------+-----------------------------------+---------------+---------------------+

*Maximize Window* **waits and maximizes the size of a window**. The keyword waits the given **timeout** (an **amount of seconds**) and it maximizes a window with a given **title name** (that fits the given **regular expression**). When the timeout is expired without having found a window with a proper title, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.

The keyword can return ``${wait_time}``, which is the **amount of seconds** before the keyword has correctly **match the given regular expression** with an ongoing window.

.. note::
    It is a best practice to **maximize the window** on which the rest of test case will work, because it can **limit the graphical noise** coming from the rest of the GUI on screen. This can optimize the detection of the Alyvix visual keywords on the interested application window.


.. _system_keywords-window_keywords-show_window:

Show Window
-----------

    +-----------------+---------------------------+
    | ``Show Window`` | ``<window_title_regexp>`` |
    +-----------------+---------------------------+

Example:

    +-----------------+-----------------------------------+
    | ``Show Window`` | ``synthetic.*monitoring.*alyvix`` |
    +-----------------+-----------------------------------+

*Show Window* **brings in foreground a window** (without resizing it) with a given **title name** (that fits the given **regular expression**). This keyword has an **immediate timeout** and **no exception**.



.. _system_keywords-window_keywords-check_window:

Check Window
------------

    +------------------+---------------------------+
    | ``Check Window`` | ``<window_title_regexp>`` |
    +------------------+---------------------------+

Example:

    +----------+------------------+-----------------------------------+
    | ``${x}`` | ``Check Window`` | ``synthetic.*monitoring.*alyvix`` |
    +----------+------------------+-----------------------------------+
    | ``Log``  | ``${x}``         |                                   |
    +----------+------------------+-----------------------------------+

*Check Window* **checks the existence of a window** (in background or in foreground) with a given **title name** (that fits the given **regular expression**). It returns ``True`` or ``False`` for further decision or logging steps. This keyword has an **immediate timeout** and **no exception**.


.. _system_keywords-window_keywords-close_window:

Close Window
------------

    +------------------+---------------------------+
    | ``Close Window`` | ``<window_title_regexp>`` |
    +------------------+---------------------------+

Example:

    +------------------+-----------------------------------+
    | ``Close Window`` | ``synthetic.*monitoring.*alyvix`` |
    +------------------+-----------------------------------+

*Close Window* **closes a window** (in background or in foreground) with a given **title name** (that fits the given **regular expression**). This keyword has an **immediate timeout** and **no exception**.


.. _system_keywords-window_keywords-wait_window_close:

Wait Window Close
-----------------

    +-----------------------+---------------------------+-----------------------+-----------------------------+
    | ``Wait Window Close`` | ``<window_title_regexp>`` | ``timeout=<seconds>`` | ``exception={True, False}`` |
    +-----------------------+---------------------------+-----------------------+-----------------------------+

    * Default values: ``timeout=60``, ``exception=True``.

Example:

    +-----------------------+-----------------------------------+
    | ``Wait Window Close`` | ``synthetic.*monitoring.*alyvix`` |
    +-----------------------+-----------------------------------+

    +-----------------------+-----------------------------------+----------------+--------------------+
    | ``Wait Window Close`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=30`` | ``exception=True`` |
    +-----------------------+-----------------------------------+----------------+--------------------+

    +------------------+-----------------------+-----------------------------------+---------------+---------------------+
    | ``${wait_time}`` | ``Wait Window Close`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=3`` | ``exception=False`` |
    +------------------+-----------------------+-----------------------------------+---------------+---------------------+

*Wait Window Close* **waits until a window is closed and is no longer active**. The keyword waits a given **timeout** (an **amount of seconds**) for the disappearance of a window with a given **title name** (that fits the given **regular expression**). When the timeout is expired without having found a window with a proper title, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.

The keyword can return ``${wait_time}``, which is the **amount of seconds** before the keyword has correctly **match the given regular expression** with an ongoing window.


.. _system_keywords-io_keywords:

I/O keywords
============


.. _system_keywords-io_keywords-send_keys:

Send Keys
---------

    +---------------+------------+-----------------------------+
    | ``Send Keys`` | ``<keys>`` | ``encrypted={True, False}`` |
    +---------------+------------+-----------------------------+

    * Default values: ``encrypted=False``.

    * Key syntax:

    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Enter}`                              | **ENTER** key                                                                                                                       |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Space}`                              | **SPACE** key (only needed at the beginning or the end of the string)                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Tab}`                                | **TAB** key                                                                                                                         |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Shift}`                              | **SHIFT** key; :literal:`{LShift}` for Left SHIFT key; :literal:`{RShift}` for Right SHIFT key                                      |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Shift Down}` - :literal:`{Shift Up}` | :literal:`{Shift Down}` holds the **SHIFT** key down until :literal:`{Shift Up}` is sent                                            |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Ctrl}`                               | **CONTROL** key; :literal:`{LCtrl}` for Left CONTROL key; :literal:`{RCtrl}` for Right CONTROL key                                  |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Ctrl Down}` - :literal:`{Ctrl Up}`   | :literal:`{Ctrl Down}` holds the **CONTROL** key down until :literal:`{Ctrl Up}` is sent                                            |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Alt}`                                | **ALT** key; :literal:`{LAlt}` for Left ALT key; :literal:`{RAlt}` for Right ALT key                                                |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Alt Down}` - :literal:`{Alt Up}`     | :literal:`{Alt Down}` holds the **ALT** key down until :literal:`{Alt Up}` is sent                                                  |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{LWin Down}` - :literal:`{LWin Up}`   | :literal:`{LWin Down}` holds the left **WindowsLogo** key down until :literal:`{LWin Up}` is sent                                   |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{~}`                                  | **~**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{!}`                                  | **!**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{#}`                                  | **#**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`%`                                    | **%**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{^}`                                  | **^**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{+}`                                  | **\+**                                                                                                                              |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`\``                                   | **\`**                                                                                                                              |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{{}`                                  | **{**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{}}`                                  | **}**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{(}`                                  | **(**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{)}`                                  | **)**                                                                                                                               |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{U+nnnn}`                             | `Unicode character <http://www.unicode.org/charts/>`_; :literal:`nnnn` is its hexadecimal value, excluding the :literal:`0x` prefix |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Backspace}`                          | **Backspace** key                                                                                                                   |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Del}`                                | **Delete** key                                                                                                                      |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Esc}`                                | **ESCAPE** key                                                                                                                      |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{F1}` - :literal:`{F24}`              | **Function** keys                                                                                                                   |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Up}`                                 | **Up-arrow** key                                                                                                                    |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Down}`                               | **Down-arrow** key                                                                                                                  |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Left}`                               | **Left-arrow** key                                                                                                                  |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Right}`                              | **Right-arrow** key                                                                                                                 |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{Home}`                               | **Home** key                                                                                                                        |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{End}`                                | **End** key                                                                                                                         |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{PgUp}`                               | **Page-up** key                                                                                                                     |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{PgDn}`                               | **Page-down** key                                                                                                                   |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
    | :literal:`{PgDn}`                               | **Page-down** key                                                                                                                   |
    +-------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+

Example:

    +---------------+----------------------------+---------------------+------------------+
    | ``Send Keys`` | ``admin{Tab}``             |                     |                  |
    +---------------+----------------------------+---------------------+------------------+
    | ``Send Keys`` | ``admin``                  | ``encrypted=False`` |                  |
    +---------------+----------------------------+---------------------+------------------+
    | ``Send Keys`` | ``{Enter}``                |                     |                  |
    +---------------+----------------------------+---------------------+------------------+
    | ``Send Keys`` | ``info@alyvix.com``        | ``delay=200``       | ``duration=200`` |
    +---------------+----------------------------+---------------------+------------------+
    | ``Send Keys`` | ``{Alt Down}{F4}{Alt Up}`` |                     |                  |
    +---------------+----------------------------+---------------------+------------------+

*Send Keys* **types a sequence of keystrokes** to the active window where the focus is: **regular characters** (letters and numbers) can be stated as they are, while **special keys** have to be enclosed in braces (have a look at the table above for their syntax, e.g. ``{enter}``). The **encrypted option** can be activated (i.e. ``encrypted=True``) in case the string of keystrokes has been encrypted using the Alyvix :ref:`encryption tool <encryption_tool>`. **Delays** [ms] sets the sleep intervals (in milliseconds) between keys. **Duration** [ms] sets how long (in milliseconds) keys are going to be pressed.


.. _system_keywords-io_keywords-mouse_scroll:

Mouse Scroll
------------

    +------------------+---------------------+--------------------------+
    | ``Mouse Scroll`` | ``steps=<scrolls>`` | ``direction={down, up}`` |
    +------------------+---------------------+--------------------------+

    * Default values: ``steps=2``, ``direction=up``.

Example:

    +------------------+-------------+--------------------+
    | ``Mouse Scroll`` | ``steps=3`` | ``direction=down`` |
    +------------------+-------------+--------------------+

*Mouse Scroll* **scrolls the active window**. The keyword scrolls the windows of the given **steps**, **up or down** and where the focus is.

.. note::
    *Mouse Scroll* is **useful for scanning windows** (e.g. website in a browser) searching for graphic elements defined in :ref:`visual keywords <visual_keywords>`.


.. _system_keywords-io_keywords-move_mouse:

Mouse Move
----------

    +----------------+---------------------------------------+-------------------------------------+
    | ``Mouse Move`` | ``x=<horizontal_pixel_coordinate_x>`` | ``y=<vertical_pixel_coordinate_y>`` |
    +----------------+---------------------------------------+-------------------------------------+

Example:

    +----------------+---------+---------+
    | ``Mouse Move`` | ``x=0`` | ``y=0`` |
    +----------------+---------+---------+

*Mouse Move* **moves the mouse pointer** to the given horizontal and vertical **pixel coordinates** of your screen.

.. note::
    Keep in mind that the **positive verse of the horizontal screen coordinate** x is from left to right. The **positive verse of the vertical screen coordinate** y is from top to bottom. So that, the **origin of screen axes** is at the point ``x=0`` ``y=0`` in the top-left corner. Sometimes leaving the mouse pointer in a certain position after a transaction can cause unintended interactions that can follow.


.. _system_keywords-performance_keywords:

Performance keywords
====================


.. _system_keywords-performance_keywords-add_perfdata:

Add Perfdata
------------

    +------------------+------------------------+---------------------+---------------------------------+----------------------------------+------------------------+-----------------------------+
    | ``Add Perfdata`` | ``<performance_name>`` | ``value=<seconds>`` | ``warning_threshold=<seconds>`` | ``critical_threshold=<seconds>`` | ``state={0, 1, 2, 3}`` | ``timestamp={True, False}`` |
    +------------------+------------------------+---------------------+---------------------------------+----------------------------------+------------------------+-----------------------------+

    * Default values: ``value=None``, ``warning_threshold=None``, ``critical_threshold=None``, ``state=2``, ``timestamp=False``.

Example:

    * Declaration:

    +------------------+------------------+
    | ``Add Perfdata`` | ``citrix_login`` |
    +------------------+------------------+

    * Definition:

    +------------------+---------------------+-----------------------------------+-------------------------+----------------------------+--------------------+
    | ``${wait_time}`` | ``Maximize Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=10``          |                            |                    |
    +------------------+---------------------+-----------------------------------+-------------------------+----------------------------+--------------------+
    | ``Add Perfdata`` | ``dummy_perf``      | ``value=${wait_time}``            | ``warning_threshold=5`` | ``critical_threshold=7.5`` | ``timestamp=True`` |
    +------------------+---------------------+-----------------------------------+-------------------------+----------------------------+--------------------+

*Add Perfdata* **declares a performance measure** in terms of its **name**. The latter could be the name of a :ref:`visual keyword <visual_keywords>`: when that keyword runs and then successfully exits, finding the defined graphic elements, it fills the performance with its **measurement**, **thresholds** and **timestamp**.

*Add Perfdata* **can also define a performance measure** in terms of its **name**, **value**, **thresholds** and **timestamp**: it fills a performance, in the middle of a test case, with a **measurement** (e.g. from a system keyword as :ref:`Wait Window <system_keywords-window_keywords-wait_window>`), **thresholds** and **timestamp**

.. _system_keywords-performance_keywords-add_perfdata-nagios_exitcode:
.. note::
    The ``state`` argument (eventually in a declaration) sets the ``errorlevel`` code that returns from a :ref:`visual keyword <visual_keywords>` just in case it breaks **without its performance measure**. **Nagios codes** have the following meanings:

        * ``0`` **OK**
        * ``1`` **WARNING**
        * ``2`` **CRITICAL**
        * ``3`` **UNKNOWN**

    On the other hand, if a keyword returns a measure then **thresholds determine the exit code**.

.. warning::
    It is convenient to **declare all performance measures at the beginning of test cases** in a :ref:`setup section <testcase_sections-main_sections-setup_section>`: in this way it is known at which point the test case eventually breaks. If the value of a performance measure is not filled at the end of a test case (e.g. the test case breaks before or at that point) the keyword state code returns (``2``, **CRITICAL**, by default).


.. _system_keywords-performance_keywords-print_perfdata:

Print Perfdata
--------------

    +--------------------+----------------------+--------------------------------+
    | ``Print Perfdata`` | ``message=<string>`` | ``print_output={True, False}`` |
    +--------------------+----------------------+--------------------------------+

    * Default values: ``message=None``, ``print_output=True``.

Example:

    +--------------------+
    | ``Print Perfdata`` |
    +--------------------+

*Print Perfdata* **prints all the performance measures** that have been declared (or just filled, but not declared). By default, a **message is printed out** at the end of a test case execution to **describe its overall state** and eventually the name of the last performance that has been measured before a failure.


.. _system_keywords-performance_keywords-store_perfdata:

Store Perfdata
--------------

    +--------------------+----------------------------+
    | ``Store Perfdata`` | ``dbname=<database_path>`` |
    +--------------------+----------------------------+

    * Default values: ``dbname=<testcase_path>\\<testcase_name>.db``.


Example:

    +--------------------+
    | ``Store Perfdata`` |
    +--------------------+

    +--------------------+----------------------------------------------+
    | ``Store Perfdata`` | ``C:\\alyvix_testcases\\citrix_word.sqlite`` |
    +--------------------+----------------------------------------------+

.. warning::
    Type the **database path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<database_path>\\<database_name>.sqlite``).

*Store Perfdata* **saves the test case data in a SQLite database** file with a proper :ref:`database structure <database_structure-store_perfdata>`. New data are added to past database entries (that comes from previous test case executions): in this way, an Alyvix probe can keep track of test case data.


.. _system_keywords-performance_keywords-store_scrapdata:

Store Scrapdata
---------------

    +---------------------+----------------------------+
    | ``Store Scrapdata`` | ``dbname=<database_path>`` |
    +---------------------+----------------------------+

    * Default values: ``dbname=<testcase_path>\\<testcase_name>.db``.


Example:

    +---------------------+
    | ``Store Scrapdata`` |
    +---------------------+

    +---------------------+----------------------------------------------+
    | ``Store Scrapdata`` | ``C:\\alyvix_testcases\\citrix_word.sqlite`` |
    +---------------------+----------------------------------------------+

.. warning::
    Type the **database path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<database_path>\\<database_name>.sqlite``).

*Store Scrapdata* **saves the scraped text in a SQLite database** file with a proper :ref:`database structure <database_structure-store_scrapdata>`. New scraped text is added after each scraper execution.


.. _system_keywords-performance_keywords-publish_perfdata:

Publish Perfdata
----------------

    +----------------------+--------------+--------------------------------------------------+----------------------------------------+-----------------------------------------+------------------------------+
    | ``Publish Perfdata`` | ``type=csv`` | ``start_date={<yyyy-mm-dd hh:mm>, days, hours}`` | ``end_date={<yyyy-mm-dd hh:mm>, now}`` | ``filename=<path_to>\\<file_name>.csv`` | ``suffix={None, timestamp}`` |
    +----------------------+--------------+--------------------------------------------------+----------------------------------------+-----------------------------------------+------------------------------+

    +----------------------+---------------+-----------------------------------+-------------------------+------------------------+-----------------------------+------------------------------+
    | ``Publish Perfdata`` | ``type=nats`` | ``testcase_name=<testcase_name>`` | ``server=<ip_address>`` | ``port=<port_number>`` | ``subject=<database_name>`` | ``measurement=<table_name>`` |
    +----------------------+---------------+-----------------------------------+-------------------------+------------------------+-----------------------------+------------------------------+

    * Default values: ``type=csv``, ``filename=<testcase_path>\\<testcase_name>.csv``, ``suffix=None``, ``testcase_name=<testcase_name>``

Example:

    * CSV mode:

    +----------------------+--------------+---------------------------------+-------------------------------+---------------------------------------------------+----------------------+
    | ``Publish Perfdata`` | ``type=csv`` | ``start_date=2016-02-01 00:01`` | ``end_date=2016-08-04 23:59`` | ``filename=C:\\alyvix_reports\\citrix_login.csv`` | ``suffix=timestamp`` |
    +----------------------+--------------+---------------------------------+-------------------------------+---------------------------------------------------+----------------------+

    +----------------------+------------------------+------------------+
    | ``Publish Perfdata`` | ``start_date=1 weeks`` | ``end_date=now`` |
    +----------------------+------------------------+------------------+

    * NATS mode:

    +----------------------+---------------+----------------------+---------------+----------------------+------------------------+
    | ``Publish Perfdata`` | ``type=nats`` | ``server=127.0.0.1`` | ``port=4222`` | ``subject=customer`` | ``measurement=alyvix`` |
    +----------------------+---------------+----------------------+---------------+----------------------+------------------------+

.. warning::
    Type the **CSV file path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path_to>\\<csv_filename>.csv``). To publish test case data in a **CSV file** is necessary to **store test case data in advance** using :ref:`Store Perfdata <system_keywords-performance_keywords-store_perfdata>`.

*Publish Perfdata* **publishes test case data** in a **CSV file** or in an **InfluxDB** (through **NATS** and Telegraf) as follows:


.. _system_keywords-performance_keywords-publish_perfdata-csv_mode:

CSV mode
^^^^^^^^

``type=csv`` takes mandatory ``start_date`` and ``end_date`` in the following formats ``<yyyy>-<mm>-<dd> <hh>:<mm>``, ``<n> days`` or ``<n> hours``; ``now`` just as end date. It can also take an optional **path** ``filename`` to **save a CSV** with or without a **timestamp** ``suffix``.


.. _system_keywords-performance_keywords-publish_perfdata-nats_mode:

NATS mode
^^^^^^^^^

``type=nats`` takes mandatory ``server``, ``port``, ``subject`` and ``measurement`` and **flush to a NATS server all the collected performance** in the following format, which is the `InfluxDB Line Protocol <https://docs.influxdata.com/influxdb/v1.3/write_protocols/line_protocol_tutorial/>`_:

    +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------+
    | ``<measurement>,<tag_1>,..,<tag_n>``                                                                                                                                                      | ``<field_1>,..,<field_n>``                                                                                                                                                                                                  | ``<timestamp>``                   |
    +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------+
    | ``<table_name>,host=<machine_hostname>,username=<windows_username>,test_name=<testcase_name>,transaction_name=<transaction_name>,state={ok, warning, critical, timed_out, not_executed}`` | ``warning_threshold=<milliseconds>,critical_threshold=<milliseconds>,timeout_threshold=<milliseconds>,performance=<milliseconds>,cumulative=<milliseconds>,error_level={0, 1, 2, 3},run_code=<unique_test_execution_code>`` | ``<nanoseconds_epoch_timestamp>`` |
    +-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------+

.. note::
    Points must be formatted in the **InfluxDB Line Protocol** to be successfully parsed and written in InfluxDB through NATS and Telegraf. A single line of the Line Protocol represents one data point with the following features:

    * ``host``: Alyvix probe hostname
    * ``username``: username of the user logged in Windows
    * ``test_name``: testcase name
    * ``transaction_name``: transaction name
    * ``state``: :ref:`Nagios exit label <system_keywords-performance_keywords-add_perfdata-nagios_exitcode>` ``OK``, ``WARNING``, ``CRITICAL`` or ``UNKNOWN``
    * ``warning_threshold``: transaction warning threshold in [milliseconds]
    * ``critical_threshold``: transaction critical threshold in [milliseconds]
    * ``timeout_threshold``: transaction timeout threshold in [milliseconds]
    * ``performance``: transaction performance measure in [milliseconds]
    * ``cumulative``: cumulative measure in [milliseconds] of all the collected performance including the current transaction
    * ``error_level``: :ref:`Nagios exit code <system_keywords-performance_keywords-add_perfdata-nagios_exitcode>` ``0``, ``1``, ``2`` or ``3``
    * ``run_code``: unique alphanumeric test case execution code
    * ``time``: epoch in [nanoseconds] about the transaction start time


.. _system_keywords-performance_keywords-rename_perfdata:

Rename Perfdata
---------------

    +---------------------+-------------------------------------+-------------------------------------+----------------------------+-----------------------------+
    | ``Rename Perfdata`` | ``old_name=<old_performance_name>`` | ``new_name=<new_performance_name>`` | ``warning_threshold=None`` | ``critical_threshold=None`` |
    +---------------------+-------------------------------------+-------------------------------------+----------------------------+-----------------------------+

    * Optional arguments: ``warning_threshold=None``, ``critical_threshold=None``.

Example:

    +---------------------+---------------------------------+----------------------------+--------------------------+----------------------------+
    | ``Rename Perfdata`` | ``old_name=login_generic_step`` | ``new_name=login_step_01`` | ``warning_threshold=5``  | ``critical_threshold=7.5`` |
    +---------------------+---------------------------------+----------------------------+--------------------------+----------------------------+

    +---------------------+---------------------------------+----------------------------+
    | ``Rename Perfdata`` | ``old_name=login_generic_step`` | ``new_name=login_step_02`` |
    +---------------------+---------------------------------+----------------------------+

*Rename Perfdata* **copies the performance data of an existing keyword under a new performance name**. At least, you have to set the ``old_name`` and the ``new_name`` keywords, but it is also **possible to redefine warning and critical thresholds**.

.. note::
    This could be useful in order to **reuse the same keyword with different arguments** keeping track of the performance measure after each execution. For example, you could run an :ref:`Object Finder <visual_keywords-object_finder>` searching for the same image as the main component, but for a different text string as the sub component (passed as an argument). **Renaming a keyword allows to keep track of its performance measures after each use**, it is like to save that measure as a brand new keyword. At the end of the test, before :ref:`Print Perfdata <system_keywords-performance_keywords-print_perfdata>`, it could be the case to :ref:`delete the old partial keywords <system_keywords-performance_keywords-delete_perfdata>`.

    Example:

        +---------------------+----------------------------+-------------------------------+
        | ``Add Perfdata``    | ``customer_code_01``       |                               |
        +---------------------+----------------------------+-------------------------------+
        | ``Add Perfdata``    | ``customer_code_02``       |                               |
        +---------------------+----------------------------+-------------------------------+
        |                     |                            |                               |
        +---------------------+----------------------------+-------------------------------+
        | ``customer_code``   | ``1``                      |                               |
        +---------------------+----------------------------+-------------------------------+
        | ``Rename Perfdata`` | ``old_name=customer_code`` | ``new_name=customer_code_01`` |
        +---------------------+----------------------------+-------------------------------+
        |                     |                            |                               |
        +---------------------+----------------------------+-------------------------------+
        | ``customer_code``   | ``2``                      |                               |
        +---------------------+----------------------------+-------------------------------+
        | ``Rename Perfdata`` | ``old_name=customer_code`` | ``new_name=customer_code_02`` |
        +---------------------+----------------------------+-------------------------------+
        |                     |                            |                               |
        +---------------------+----------------------------+-------------------------------+
        | ``Delete Perfdata`` | ``customer_code``          |                               |
        +---------------------+----------------------------+-------------------------------+
        | ``Print Perfdata``  |                            |                               |
        +---------------------+----------------------------+-------------------------------+

.. warning::
    Executing two or more times the same :ref:`visual keyword <visual_keywords>` simply **overrides its current performance measure**, so loosing the previous one. *Rename Perfdata* **avoids the need to define a new visual** keyword with the same graphic elements to detect.


.. _system_keywords-performance_keywords-sum_perfdata:

Sum Perfdata
------------

    +------------------+--------------------------+--------+--------------------------+---------------------------------+----------------------------+-----------------------------+
    | ``Sum Perfdata`` | ``<performance_name_1>`` | ``..`` | ``<performance_name_n>`` | ``name=<new_performance_name>`` | ``warning_threshold=None`` | ``critical_threshold=None`` |
    +------------------+--------------------------+--------+--------------------------+---------------------------------+----------------------------+-----------------------------+

    * Optional arguments: ``<performance_name_3>``, .., ``<performance_name_n>``

    * Default values: ``warning_threshold=None``, ``critical_threshold=None``

Example:

    +------------------+-------------------+-------------------+----------------------+-------------------------+----------------------------+
    | ``Sum Perfdata`` | ``login_step_01`` | ``login_step_02`` | ``name=login_steps`` | ``warning_threshold=5`` | ``critical_threshold=7.5`` |
    +------------------+-------------------+-------------------+----------------------+-------------------------+----------------------------+

    +------------------+-------------------+-------------------+----------------------+
    | ``Sum Perfdata`` | ``login_step_01`` | ``login_step_02`` | ``name=login_steps`` |
    +------------------+-------------------+-------------------+----------------------+

*Sum Perfdata* **sums the given performance measures in a new one**. At least, you have to set **two** ``<performance_name>`` **to sum** in the ``<new_performance_name>``. It is also possible to **define warning and critical thresholds** of the new keyword.

.. note::
    At the end of the test, before :ref:`Print Perfdata <system_keywords-performance_keywords-print_perfdata>`, it could be the case to :ref:`delete the old partial keywords <system_keywords-performance_keywords-delete_perfdata>`.


.. _system_keywords-performance_keywords-add_perfdata_tag:

Add Perfdata Tag
----------------

    +----------------------+----------------------------------+-------------------------+---------------------------+
    | ``Add Perfdata Tag`` | ``perf_name={<perf_name>, all}`` | ``tag_name=<tag_name>`` | ``tag_value=<tag_value>`` |
    +----------------------+----------------------------------+-------------------------+---------------------------+

Example:

    +----------------------+-------------------------------+-------------------------+---------------------+
    | ``Add Perfdata Tag`` | ``perf_name=ax12_home_ready`` | ``tag_name=aos_name``   | ``tag_value=bla01`` |
    +----------------------+-------------------------------+-------------------------+---------------------+
    | ``Add Perfdata Tag`` | ``perf_name=all``             | ``tag_name=id_session`` | ``tag_value=1``     |
    +----------------------+-------------------------------+-------------------------+---------------------+

*Add Perfdata Tag* **adds a custom tag to** a performance point or to all **performance points** of a test case. It could be useful for publishing performance in :ref:`NATS mode<system_keywords-performance_keywords-publish_perfdata-nats_mode>`.


.. _system_keywords-performance_keywords-add_perfdata_field:

Add Perfdata Field
------------------

    +------------------------+----------------------------------+-----------------------------+-------------------------------+
    | ``Add Perfdata Field`` | ``perf_name={<perf_name>, all}`` | ``field_name=<field_name>`` | ``field_value=<field_value>`` |
    +------------------------+----------------------------------+-----------------------------+-------------------------------+

Example:

    +------------------------+-------------------------------+---------------------------+-----------------------+
    | ``Add Perfdata Field`` | ``perf_name=ax12_home_ready`` | ``field_name=aos_name``   | ``field_value=bla01`` |
    +------------------------+-------------------------------+---------------------------+-----------------------+
    | ``Add Perfdata Field`` | ``perf_name=all``             | ``field_name=id_session`` | ``field_value=1``     |
    +------------------------+-------------------------------+---------------------------+-----------------------+

*Add Perfdata Field* **adds a custom field to** a performance point or to all **performance points** of a test case. It could be useful for publishing performance in :ref:`NATS mode<system_keywords-performance_keywords-publish_perfdata-nats_mode>`.


.. _system_keywords-performance_keywords-delete_perfdata:

Delete Perfdata
---------------

    +---------------------+-----------------------------+
    | ``Delete Perfdata`` | ``name=<performance_name>`` |
    +---------------------+-----------------------------+

Example:

    +---------------------+-------------------+
    | ``Delete Perfdata`` | ``login_step_01`` |
    +---------------------+-------------------+

*Delete Perfdata* **deletes an existing performance measure**. It is useful after :ref:`Rename Perfdata <system_keywords-performance_keywords-rename_perfdata>` or :ref:`Delete Perfdata <system_keywords-performance_keywords-delete_perfdata>` and before :ref:`Print Perfdata <system_keywords-performance_keywords-print_perfdata>` to clean the final test case outcome.


.. _system_keywords-network_keywords:

Network keywords
================


.. _system_keywords-network_keywords-get_mstsc_hostname:

Get Mstsc Hostname
------------------

    +------------------------+--------------------------------------------+--------------------------------------+
    | ``Get Mstsc Hostname`` | ``customer_name=<prefix_ip_hostname_map>`` | ``path_json=<path_ip_hostname_map>`` |
    +------------------------+--------------------------------------------+--------------------------------------+

    * Default values: ``path_json=<testcase_path>``

Example:

    +-----------------------+-----------------------------+-----------------------+---------------------------------+
    | ``${mstsc_hostname}`` | ``Get Mstsc Hostname``      | ``probename``         |                                 |
    +-----------------------+-----------------------------+-----------------------+---------------------------------+
    | ``Add Perfdata Tag``  | ``perf_name=desktop_ready`` | ``tag_name=hostname`` | ``tag_value=${mstsc_hostname}`` |
    +-----------------------+-----------------------------+-----------------------+---------------------------------+

    +-----------------------+------------------------+---------------+------------------------------------------------------------------------------+
    | ``${mstsc_hostname}`` | ``Get Mstsc Hostname`` | ``probename`` | ``C:\\Python27\\Lib\\site-packages\\alyvix\\robotproxy\\alyvix_testcases\\`` |
    +-----------------------+------------------------+---------------+------------------------------------------------------------------------------+

.. warning::
  Type the **folder path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path_ip_hostname_map>\\``).

*Get Mstsc Hostname* **provides the** ``mstsc`` **hostname that is mapped in the** :download:`probename_ip_hostname_map.json <./probename_ip_hostname_map.json>` in a given path (e.g. ``C:\Python27\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\``) which is the test case folder by default.

    .. code-block:: json

        {
            "127.0.0.1": "hostname_1",
            "127.0.0.2": "hostname_2"
        }


.. _system_keywords-screenshot_keywords:

Screenshot keywords
===================


.. _system_keywords-screenshot_keywords-alyvix_screenshot:

Alyvix Screenshot
-----------------

    +-----------------------+----------------------------------------------------+
    | ``Alyvix Screenshot`` | ``filename_arg=<screenshot_filename>{.png, .jpg}`` |
    +-----------------------+----------------------------------------------------+

Example:

    +-----------------------+----------------------+
    | ``Alyvix Screenshot`` | ``login_screen.jpg`` |
    +-----------------------+----------------------+

*Alyvix Screenshot* **grabs a screenshot and saves it into the output folder**, which can be specified as an argument ``--outputdir <output_folder_path>`` (e.g. ``--outputdir "C:\alyvix_reports\login_testcase"``) of the Alyvix :ref:`test case script <commandline_output>`. By default the extension of the screenshot file is ``.png``, but it is also possible to specify ``.jpg`` as the image compression.


.. _system_keywords-debug_keywords:

Debug keywords
==============


.. _system_keywords-debug_keywords-alyvix_config:

Alyvix Config
-------------

    +-------------------+------------------------------------------+
    | ``Alyvix Config`` | ``full_filename=<config.xml_file_path>`` |
    +-------------------+------------------------------------------+

Example:

    +-------------------+---------------------------------------------------+
    | ``Alyvix Config`` | ``full_filename=C:\\alyvix_logbooks\\config.xml`` |
    +-------------------+---------------------------------------------------+

.. warning::
  Type the **folder path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path_to>\\config.xml``).

*Alyvix Config* **links the** :download:`config.xml <./config.xml>` **file to set some Alyvix custom settings**.

    .. code-block:: xml

        <?xml version="1.0" encoding="UTF-8"?>
        <config>
            <finder>
                <finder_thread_interval>0.5</finder_thread_interval>
                <check_diff_interval>0.1</check_diff_interval>
                <wait_timeout>20</wait_timeout>
            </finder>
            <log>
                <enable>True</enable>
                <home>C:\alyvix_logbooks</home>
                <retention>
                    <max_days>7</max_days>
                    <hours_per_day>24</hours_per_day>
                </retention>
            </log>
        </config>

Edit ``config.xml`` to enable the Alyvix **debugging mode** (``<log><enable>True``) and set in which folder storing the **detection screenshots** of Alyvix objects (``<log><home>C:\<path_to_folder>``). It is also possible to set the **time periods of the frame grabber** ``<finder><finder_thread_interval>0.5`` (0.5s by default) and **of the object detector** ``<finder><check_diff_interval>0.1`` (0.1s by default).

.. note::
  It is recommended to **leave the default values** (i.e. ``0.5`` for the detector and ``0.1`` for the grabber), in order to avoid overloading the hardware. But you can **increase the measurement accuracy** decreasing the detector period ``<finder><finder_thread_interval>`` and you can **increase the measurement precision** decreasing the grabber period ``<finder><check_diff_interval>``.


.. _system_keywords-debug_keywords-set_alyvix_info:

Set Alyvix Info
---------------

    +---------------------+-------------------------+---------------------------+
    | ``Set Alyvix Info`` | ``name=<setting_name>`` | ``value=<setting_value>`` |
    +---------------------+-------------------------+---------------------------+

Example:

    +---------------------+-------------------------------------------+---------------+
    | ``Set Alyvix Info`` | ``name=CHECK DIFF INTERVAL``              | ``value=0.1`` |
    +---------------------+-------------------------------------------+---------------+
    | ``Set Alyvix Info`` | ``name=FINDER THREAD INTERVAL``           | ``value=0.5`` |
    +---------------------+-------------------------------------------+---------------+
    | ``Set Alyvix Info`` | ``name=CHECK DIFF INTERVAL DISAPPEAR``    | ``value=0.1`` |
    +---------------------+-------------------------------------------+---------------+
    | ``Set Alyvix Info`` | ``name=FINDER THREAD INTERVAL DISAPPEAR`` | ``value=0.5`` |
    +---------------------+-------------------------------------------+---------------+
    | ``Set Alyvix Info`` | ``name=ACTIONS DELAY``                    | ``value=0.5`` |
    +---------------------+-------------------------------------------+---------------+
    | ``Set Alyvix Info`` | ``name=channel``                          | ``value=r``   |
    +---------------------+-------------------------------------------+---------------+

*Set Alyvix Info* **sets values of the Alyvix engine settings**. *Set Alyvix Info* acts from its call point until the end of the test case (or until another setup).

*Set Alyvix Info* can set the following properties:

    * ``CHECK DIFF INTERVAL`` redefines the **amount of seconds** (e.g. ``0.1``) that **Alyvix waits before grabbing a new screen frame** (on which it tries to detect the appearance of graphic elements); you can consider this setting as the **measurement precision of the graphic appearance detection**; the default value is ``0.1``;

    * ``CHECK DIFF INTERVAL DISAPPEAR`` redefines the **amount of seconds** (e.g. ``0.1``) that **Alyvix waits before grabbing a new screen frame** (on which it tries to detect the disappearance of graphic elements); you can consider this setting as the **measurement precision of the graphic disappearance detection**; the default value is ``0.1``;

    * ``FINDER THREAD INTERVAL`` redefines the **amount of seconds** (e.g. ``0.5``) that **Alyvix takes between attempts to detect the appearance of graphic elements**; you can consider this setting as the **measurement accuracy of the graphic appearance detection**; the default value is ``0.5``;

    * ``FINDER THREAD INTERVAL DISAPPEAR`` redefines the **amount of seconds** (e.g. ``0.5``) that **Alyvix takes between attempts to detect the disappearance of graphic elements**; you can consider this setting as the **measurement accuracy of the graphic disappearance detection**; the default value is ``0.5``;

    * ``ACTIONS DELAY`` to redefine the **amount of seconds** (e.g. ``0.5``) that **Alyvix takes after each interaction step**; the default value is ``0.5``.

    * ``channel`` to **select just one single color channel** (``r`` as red, ``g`` as green or ``b`` as blue) and **cutoff the other two**; the default value is ``all``.
