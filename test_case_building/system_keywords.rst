.. _system_keywords:

***************
System keywords
***************


.. _system_keywords-process_keywords:

Process keywords
================


.. _system_keywords-process_keywords-create_process:

Create Process
--------------

    +--------------------+-----------------------------------+
    | ``Create Process`` | ``<application executable path>`` |
    +--------------------+-----------------------------------+

    * Default arguments:

        +-----------------------------------+---+---+-----------------------------------+
        | ``<application argument 1>=None`` | . | . | ``<application argument n>=None`` |
        +-----------------------------------+---+---+-----------------------------------+

Example:

    +--------------------+--------------------------------------------------------------------------+----------------------------+----------------+
    | ``Create Process`` | ``C:\\Program Files (x86)\\ Google\\ Chrome\\ Application\\ chrome.exe`` | ``https://www.alyvix.com`` | ``-incognito`` |
    +--------------------+--------------------------------------------------------------------------+----------------------------+----------------+

.. warning::
    Type the **application executable path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path to folder>\\ <application executable>.exe``).

*Create Process* **runs executable files** (reachable to the given path, e.g. browser application, batch file) **with its optional arguments** (e.g. website address, browser options). This keyword is useful, for example, to run a browser (e.g. Internet Explorer, Chrome) with a website address to point and eventually the option for private browsing.


.. _system_keywords-process_keywords-kill_process:

Kill Process
------------

    +------------------+---------------------------+
    | ``Kill Process`` | ``<executable filename>`` |
    +------------------+---------------------------+

Example:

    +------------------+----------------+
    | ``Kill Process`` | ``chrome.exe`` |
    +------------------+----------------+

*Kill Process* **kills a process** of which you provide its executable filename. Have a look at the *Windows Task Manager*, in the *Detail* tab, to know the ongoing programs.

    .. image:: pictures/task_manager.png


.. _system_keywords-process_keywords-wait_process_close:

Wait Process Close
------------------

    +------------------------+------------------------+
    | ``Wait Process Close`` | ``<process filename>`` |
    +------------------------+------------------------+

    * Default arguments:

        +--------------+----------------+--------------------+
        | ``pid=None`` | ``timeout=60`` | ``exception=True`` |
        +--------------+----------------+--------------------+

    * Value types: ``pid=<pid number>``, ``timeout=<seconds>``, ``exception={True, False}``.

Example:

    +------------------------+---------------+
    | ``Wait Process Close`` | ``mstsc.exe`` |
    +------------------------+---------------+

    +------------------------+---------------+--------------+
    | ``Wait Process Close`` | ``mstsc.exe`` | ``pid=5123`` |
    +------------------------+---------------+--------------+

    +------------------+------------------------+---------------+---------------+---------------------+
    | ``${wait time}`` | ``Wait Process Close`` | ``mstsc.exe`` | ``timeout=3`` | ``exception=False`` |
    +------------------+------------------------+---------------+---------------+---------------------+

*Wait Process Close* **waits until an ongoing process is terminated**. The keyword waits a given **timeout** (an **amount of seconds**) for the termination of a process with a given **filename** (with its extension, e.g. ``mstsc.exe``). When the timeout is expired, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.

The keyword can return ``${wait time}``, which is the **amount of seconds** before the keyword has correctly **detect the termination of the given process**.


.. _system_keywords-window_keywords:

Window keywords
===============


.. _system_keywords-window_keywords-wait_window:

Wait Window
-----------

    +-----------------+---------------------------+
    | ``Wait Window`` | ``<window title regexp>`` |
    +-----------------+---------------------------+

    * Default arguments:

        +----------------+--------------------+
        | ``timeout=60`` | ``exception=True`` |
        +----------------+--------------------+

    * Value types: ``timeout=<seconds>``, ``exception={True, False}``.

Examples:

    +-----------------+---------------------------+
    | ``Wait Window`` | ``synthetic.*monitoring`` |
    +-----------------+---------------------------+

    +-----------------+---------------------------+--------+
    | ``Wait Window`` | ``synthetic.*monitoring`` | ``10`` |
    +-----------------+---------------------------+--------+

    +------------------+-----------------+---------------------------+-------+-----------+
    | ``${wait_time}`` | ``Wait Window`` | ``synthetic.*monitoring`` | ``3`` | ``False`` |
    +------------------+-----------------+---------------------------+-------+-----------+

*Wait Window* **waits until a window runs and is active** in the taskbar. The keyword waits the given **timeout** (an **amount of seconds**) and it waits for a window with a given **title name** (that fits a **regular expression**). When the timeout is expired without having found a window with a proper title, then the test case breaks if the **exception** is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution.

The keyword can return ``${wait_time}``, which is the **amount of seconds** before the keyword has correctly **match the given regular expression** with an ongoing window.


.. _system_keywords-window_keywords-maximize_window:

Maximize Window
---------------

    +---------------------+---------------------------+
    | ``Maximize Window`` | ``<window title regexp>`` |
    +---------------------+---------------------------+

    * Default values:

        +----------------+--------------------+
        | ``timeout=60`` | ``exception=True`` |
        +----------------+--------------------+

    * Value types: ``timeout=<seconds>``, ``exception={True, False}``.

Examples:

    +---------------------+---------------------------+
    | ``Maximize Window`` | ``synthetic.*monitoring`` |
    +---------------------+---------------------------+

    +---------------------+---------------------------+--------+
    | ``Maximize Window`` | ``synthetic.*monitoring`` | ``10`` |
    +---------------------+---------------------------+--------+

    +------------------+---------------------+---------------------------+-------+-----------+
    | ``${wait_time}`` | ``Maximize Window`` | ``synthetic.*monitoring`` | ``3`` | ``False`` |
    +------------------+---------------------+---------------------------+-------+-----------+

*Maximize Window* **waits and maximizes the size of a window**. The keyword waits the given **timeout** (an **amount of seconds**) and it maximizes a window with a given **title name** (that fits the given **regular expression**). When the timeout is expired without having found a window with a proper title, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.

The keyword can return ``${wait_time}``, which is the **amount of seconds** before the keyword has correctly **match the given regular expression** with an ongoing window.

.. note::
    It is a best practice to **maximize the window** on which the rest of test case will work, because it can **limit the graphical noise** coming from the rest of the GUI on screen. This can optimize the detection of the Alyvix visual keywords on the interested application window.


.. _system_keywords-window_keywords-show_window:

Show Window
-----------

    +-----------------+---------------------------+
    | ``Show Window`` | ``<window title regexp>`` |
    +-----------------+---------------------------+

Example:

    +-----------------+---------------------------+
    | ``Show Window`` | ``synthetic.*monitoring`` |
    +-----------------+---------------------------+

*Show Window* **brings in foreground a window** (without resizing it) with a given **title name** (that fits the given **regular expression**). This keyword has an **immediate timeout** and **no exception**.



.. _system_keywords-window_keywords-check_window:

Check Window
------------

    +------------------+---------------------------+
    | ``Check Window`` | ``<window title regexp>`` |
    +------------------+---------------------------+

Example:

    +----------+------------------+---------------------------+
    | ``${x}`` | ``Check Window`` | ``synthetic.*monitoring`` |
    +----------+------------------+---------------------------+
    | ``Log``  | ``${x}``         |                           |
    +----------+------------------+---------------------------+

*Check Window* **checks the existence of a window** (in background or in foreground) with a given **title name** (that fits the given **regular expression**). It returns ``True`` or ``False`` for further decision or logging steps. This keyword has an **immediate timeout** and **no exception**.


.. _system_keywords-window_keywords-close_window:

Close Window
------------

    +------------------+---------------------------+
    | ``Close Window`` | ``<window title regexp>`` |
    +------------------+---------------------------+

Example:

    +------------------+---------------------------+
    | ``Close Window`` | ``synthetic.*monitoring`` |
    +------------------+---------------------------+

*Close Window* **closes a window** (in background or in foreground) with a given **title name** (that fits the given **regular expression**). This keyword has an **immediate timeout** and **no exception**.


.. _system_keywords-window_keywords-wait_window_close:

Wait Window Close
-----------------

    +-----------------------+---------------------------+
    | ``Wait Window Close`` | ``<window title regexp>`` |
    +-----------------------+---------------------------+

    * Default values:

        +----------------+--------------------+
        | ``timeout=60`` | ``exception=True`` |
        +----------------+--------------------+

    * Value types: ``timeout=<seconds>``, ``exception={True, False}``.

Example:

    +-----------------------+---------------------------+
    | ``Wait Window Close`` | ``synthetic.*monitoring`` |
    +-----------------------+---------------------------+

    +-----------------------+---------------------------+--------+
    | ``Wait Window Close`` | ``synthetic.*monitoring`` | ``30`` |
    +-----------------------+---------------------------+--------+

    +------------------+-----------------------+---------------------------+-------+-----------+
    | ``${wait time}`` | ``Wait Window Close`` | ``synthetic.*monitoring`` | ``3`` | ``False`` |
    +------------------+-----------------------+---------------------------+-------+-----------+

*Wait Window Close* **waits until a window is closed and is no longer active**. The keyword waits a given **timeout** (an **amount of seconds**) for the disappearance of a window with a given **title name** (that fits the given **regular expression**). When the timeout is expired without having found a window with a proper title, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.

The keyword can return ``${wait time}``, which is the **amount of seconds** before the keyword has correctly **match the given regular expression** with an ongoing window.


.. _system_keywords-io_keywords:

I/O keywords
============


.. _system_keywords-io_keywords-send_keys:

Send Keys
---------

    +---------------+------------+
    | ``Send Keys`` | ``<keys>`` |
    +---------------+------------+

    * Default values:

        +---------------------+--------------+-----------------+
        | ``encrypted=False`` | ``delay=10`` | ``duration=-1`` |
        +---------------------+--------------+-----------------+

    * Value types: ``encrypted={True, False}``, ``delay=<milliseconds>``, ``duration=<milliseconds>``.

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

    +---------------+----------------------------+
    | ``Send Keys`` | ``admin{Tab}``             |
    +---------------+----------------------------+

    +---------------+----------------------------+-----------+
    | ``Send Keys`` | ``mAeaOg==``               | ``True``  |
    +---------------+----------------------------+-----------+

    +---------------+----------------------------+
    | ``Send Keys`` | ``{Enter}``                |
    +---------------+----------------------------+

    +---------------+----------------------------+-----------+---------+---------+
    | ``Send Keys`` | ``info@alyvix.com``        | ``False`` | ``200`` | ``200`` |
    +---------------+----------------------------+-----------+---------+---------+

    +---------------+----------------------------+
    | ``Send Keys`` | ``{Alt Down}{F4}{Alt Up}`` |
    +---------------+----------------------------+

*Send Keys* **types a sequence of keystrokes** to the active window where the focus is: **regular characters** (letters and numbers) can be stated as they are, while **special keys** have to be enclosed in braces (have a look at the table above for their syntax, e.g. ``{enter}``). The **encrypted option** can be activated (i.e. ``encrypted = True``) in case the string of keystrokes has been encrypted using the Alyvix :ref:`encryption tool <encryption_tool>`. **Delays** [ms] sets the sleep intervals (in milliseconds) between keys. **Duration** [ms] sets how long (in milliseconds) keys are going to be pressed.


.. _system_keywords-io_keywords-mouse_scroll:

Mouse Scroll
------------

    +------------------+
    | ``Mouse Scroll`` |
    +------------------+

    * Default values:

        +-------------+------------------+
        | ``steps=2`` | ``direction=up`` |
        +-------------+------------------+

    * Value types: ``steps=<scrolls>``, ``direction={down, up}``.

Example:

    +------------------+-------+----------+
    | ``Mouse Scroll`` | ``3`` | ``down`` |
    +------------------+-------+----------+

*Mouse Scroll* **scrolls the active window**. The keyword scrolls the windows of the given **steps**, **up or down** and where the focus is.

.. note::
    *Mouse Scroll* is **useful for scanning windows** (e.g. website in a browser) searching for graphic elements defined in :ref:`visual keywords <visual_keywords>`.


.. _system_keywords-io_keywords-move_mouse:

Mouse Move
----------

    +----------------+-------+-------+
    | ``Mouse Move`` | ``x`` | ``y`` |
    +----------------+-------+-------+

    * Value types: ``x=<horizontal pixel coordinate x>``, ``y=<vertical pixel coordinate y>``.

Example:

    +----------------+-------+-------+
    | ``Mouse Move`` | ``0`` | ``0`` |
    +----------------+-------+-------+

*Mouse Move* **moves the mouse pointer** to the given horizontal and vertical **pixel coordinates** of your screen.

.. note::
    Keep in mind that the **positive verse of the horizontal screen coordinate** x is from left to right. The **positive verse of the vertical screen coordinate** y is from top to bottom. So that, the **origin of screen axes** is at the point ``x = 0`` ``y = 0`` in the top-left corner. Sometimes leaving the mouse pointer in a certain position after a transaction can cause unintended interactions that can follow.


.. _system_keywords-io_keywords-get_dictionary_value:

Get Dictionary Value
--------------------

    +--------------------------+-----------------+-----------------+----------------+
    | ``Get Dictionary Value`` | ``<file json>`` | ``<dict name>`` | ``<key name>`` |
    +--------------------------+-----------------+-----------------+----------------+

    * Default values:

        +----------------------------+-------------------------------+-----------------------------+
        | ``path_file_json= 'init'`` | ``name_dict_json= 'dict_01'`` | ``name_key_json= 'key_01'`` |
        +----------------------------+-------------------------------+-----------------------------+

Example:

    +--------------+--------------------------+------------------+-------------+---------+
    | ``${value}`` | ``Get Dictionary Value`` | ``translations`` | ``italian`` | ``sky`` |
    +--------------+--------------------------+------------------+-------------+---------+

*Get Dictionary Value* **provides a value** (e.g. a text string) **associated with a dictionary** in a specified JSON file. The dictionary has to be defined **in a JSON file** like :download:`probename_customer_settings.json <./probename_customer_settings.json>`. The JSON file has to be saved in a given folder: the folder path can be passed together with the file name. The test case path (e.g. ``C:\Python27\`` ``Lib\`` ``site-packages\`` ``alyvix\`` ``robotproxy\`` ``alyvix_testcases\``) is already set by default (e.g. set ``translations`` to get values from the ``translations.json`` in the test case folder).

In the JSON file, define a dictionary (e.g. ``"italian"``) as a list of keys and their values (e.g. ``"sky": "cielo"``):

    .. code-block:: json

        {
            "dict_01": {
                "key_01": "value_01",
                "key_02": "value_02"
            },
            "dict_02": {
                "key_03": "value_03",
                "key_04": "value_04"
            }
        }


.. _system_keywords-performance_keywords:

Performance keywords
====================


.. _system_keywords-performance_keywords-add_perfdata:

Add Perfdata
------------

    +------------------+----------------+
    | ``Add Perfdata`` | ``<perfname>`` |
    +------------------+----------------+

    * Default values:

        +----------------+----------------------------+-----------------------------+
        | ``value=None`` | ``warning_threshold=None`` | ``critical_threshold=None`` |
        +----------------+----------------------------+-----------------------------+

        +-------------+---------------------+
        | ``state=2`` | ``timestamp=False`` |
        +-------------+---------------------+

    * Value types: ``value = <seconds>``, ``warning_threshold = <seconds>``, ``critical_threshold = <seconds>``, ``state = {0, 1, 2, 3}``, ``timestamp = {True, False}``.

Example:

    * Declaration:

    +------------------+------------------+
    | ``Add Perfdata`` | ``citrix_login`` |
    +------------------+------------------+

    * Definition:

    +------------------+---------------------+---------------------------+--------+---------+----------------------+
    | ``${wait_time}`` | ``Maximize Window`` | ``synthetic.*monitoring`` | ``10`` |         |                      |
    +------------------+---------------------+---------------------------+--------+---------+----------------------+
    | ``Add Perfdata`` | ``dummy_perf``      | ``${wait_time}``          | ``5``  | ``7.5`` | ``timestamp = True`` |
    +------------------+---------------------+---------------------------+--------+---------+----------------------+

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

    +--------------------+
    | ``Print Perfdata`` |
    +--------------------+

    * Default values:

        +------------------+-----------------------+
        | ``message=None`` | ``print_output=True`` |
        +------------------+-----------------------+

    * Value types: ``message = <string>``, ``print_output = {True, False}``

Example:

    +--------------------+
    | ``Print Perfdata`` |
    +--------------------+

*Print Perfdata* **prints all the performance measures** that have been declared (or just filled, but not declared). By default, a **message is printed out** at the end of a test case execution to **describe its overall state** and eventually the name of the last performance that has been measured before a failure.


.. _system_keywords-performance_keywords-store_perfdata:

Store Perfdata
--------------

    +--------------------+
    | ``Store Perfdata`` |
    +--------------------+

    * Default values:

        +------------------------------------------------+
        | ``dbname=<testcase path>\\<testcase name>.db`` |
        +------------------------------------------------+

Example:

    +--------------------+
    | ``Store Perfdata`` |
    +--------------------+

    +--------------------+----------------------------------------------+
    | ``Store Perfdata`` | ``C:\\alyvix_testcases\\citrix_word.sqlite`` |
    +--------------------+----------------------------------------------+

.. warning::
    Type the **database path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<database path>\\ <database name>.sqlite``).

*Store Perfdata* **saves the test case data in a SQLite database** file with a proper :ref:`database structure <database_structure-store_perfdata>`. New data are added to past database entries (that comes from previous test case executions): in this way, an Alyvix probe can keep track of test case data.


.. _system_keywords-performance_keywords-store_scrapdata:

Store Scrapdata
---------------

    +---------------------+
    | ``Store Scrapdata`` |
    +---------------------+

    * Default values:

        +------------------------------------------------+
        | ``dbname=<testcase path>\\<testcase name>.db`` |
        +------------------------------------------------+


Example:

    +---------------------+
    | ``Store Scrapdata`` |
    +---------------------+

    +---------------------+----------------------------------------------+
    | ``Store Scrapdata`` | ``C:\\alyvix_testcases\\citrix_word.sqlite`` |
    +---------------------+----------------------------------------------+

.. warning::
    Type the **database path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<database path>\\ <database name>.sqlite``).

*Store Scrapdata* **saves the scraped text in a SQLite database** file with a proper :ref:`database structure <database_structure-store_scrapdata>`. New scraped text is added after each scraper execution.


.. _system_keywords-performance_keywords-publish_perfdata:

Publish Perfdata
----------------

    +----------------------+--------------+----------------+--------------+
    | ``Publish Perfdata`` | ``type=csv`` | ``start_date`` | ``end_date`` |
    +----------------------+--------------+----------------+--------------+

    * Default values:

        +--------------+-----------------------------------------+-----------------+
        | ``type=csv`` | ``filename=<path to>\\<file name>.csv`` | ``suffix=None`` |
        +--------------+-----------------------------------------+-----------------+

    * Value types: ``start_date={<yyyy-mm-dd hh:mm>, days, hours}``, ``end_date={<yyyy-mm-dd hh:mm>, now}``, ``suffix={None, timestamp}``

    +----------------------+---------------+-------------------+------------+----------+-------------+-----------------+
    | ``Publish Perfdata`` | ``type=nats`` | ``testcase_name`` | ``server`` | ``port`` | ``subject`` | ``measurement`` |
    +----------------------+---------------+-------------------+------------+----------+-------------+-----------------+

    * Default values:

        +-----------------------------------+
        | ``testcase_name=<testcase name>`` |
        +-----------------------------------+

    * Value types: ``server=<ip address>``, ``port=<port number>``, ``subject=<database name>``, ``measurement=<table name>``

Example:

    * CSV mode:

    +----------------------+---------+----------------------+----------------------+-----------------------+-----------------------+
    | ``Publish Perfdata`` | ``csv`` | ``2018-01-01 00:01`` | ``2018-12-31 23:59`` | ``C:\\csv\\test.csv`` | ``suffix= timestamp`` |
    +----------------------+---------+----------------------+----------------------+-----------------------+-----------------------+

    +----------------------+---------+------------+---------+
    | ``Publish Perfdata`` | ``csv`` | ``1 days`` | ``now`` |
    +----------------------+---------+------------+---------+

    * NATS mode:

    +----------------------+----------+-----------------------+----------------+-----------------------+-------------------------+
    | ``Publish Perfdata`` | ``nats`` | ``server= 127.0.0.1`` | ``port= 4222`` | ``subject= customer`` | ``measurement= alyvix`` |
    +----------------------+----------+-----------------------+----------------+-----------------------+-------------------------+

.. warning::
    Type the **CSV file path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path to>\\ <csv filename>.csv``). To publish test case data in a **CSV file** is necessary to **store test case data in advance** using :ref:`Store Perfdata <system_keywords-performance_keywords-store_perfdata>`.

*Publish Perfdata* **publishes test case data** in a **CSV file** or in an **InfluxDB** (through **NATS** and Telegraf) as follows:


.. _system_keywords-performance_keywords-publish_perfdata-csv_mode:

CSV mode
^^^^^^^^

``type = csv`` takes mandatory ``start_date`` and ``end_date`` in the following formats ``<yyyy>-<mm>-<dd> <hh>:<mm>``, ``<n> days`` or ``<n> hours``; ``now`` just as end date. It can also take an optional **path** ``filename`` to **save a CSV** with or without a **timestamp** ``suffix``.


.. _system_keywords-performance_keywords-publish_perfdata-nats_mode:

NATS mode
^^^^^^^^^

``type = nats`` takes mandatory ``server``, ``port``, ``subject`` and ``measurement`` and **flush to a NATS server all the collected performance** with the `InfluxDB Line Protocol <https://docs.influxdata.com/influxdb/v1.3/write_protocols/line_protocol_tutorial/>`_.

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

    +---------------------+--------------+--------------+
    | ``Rename Perfdata`` | ``old_name`` | ``new_name`` |
    +---------------------+--------------+--------------+

    * Default arguments:

        +----------------------------+-----------------------------+
        | ``warning_threshold=None`` | ``critical_threshold=None`` |
        +----------------------------+-----------------------------+

    * Value types: ``old_name=<old performance name>``, ``new_name=<new performance name>``, ``warning_threshold=<seconds>``, ``critical_threshold=<seconds>``

Example:

    +---------------------+------------------------+-------------------+--------+---------+
    | ``Rename Perfdata`` | ``login_generic_step`` | ``login_step_01`` | ``5``  | ``7.5`` |
    +---------------------+------------------------+-------------------+--------+---------+

    +---------------------+------------------------+-------------------+
    | ``Rename Perfdata`` | ``login_generic_step`` | ``login_step_02`` |
    +---------------------+------------------------+-------------------+

*Rename Perfdata* **copies the performance data of an existing keyword under a new performance name**. At least, you have to set the ``old_name`` and the ``new_name`` keywords, but it is also **possible to redefine warning and critical thresholds**.

.. note::
    This could be useful in order to **reuse the same keyword with different arguments** keeping track of the performance measure after each execution. For example, you could run an :ref:`Object Finder <visual_keywords-object_finder>` searching for the same image as the main component, but for a different text string as the sub component (passed as an argument). **Renaming a keyword allows to keep track of its performance measures after each use**, it is like to save that measure as a brand new keyword. At the end of the test, before :ref:`Print Perfdata <system_keywords-performance_keywords-print_perfdata>`, it could be the case to :ref:`delete the old partial keywords <system_keywords-performance_keywords-delete_perfdata>`.

    Example:

        +---------------------+----------------------+----------------------+
        | ``Add Perfdata``    | ``customer_code_01`` |                      |
        +---------------------+----------------------+----------------------+
        | ``Add Perfdata``    | ``customer_code_02`` |                      |
        +---------------------+----------------------+----------------------+
        |                     |                      |                      |
        +---------------------+----------------------+----------------------+
        | ``customer_code``   | ``1``                |                      |
        +---------------------+----------------------+----------------------+
        | ``Rename Perfdata`` | ``customer_code``    | ``customer_code_01`` |
        +---------------------+----------------------+----------------------+
        |                     |                      |                      |
        +---------------------+----------------------+----------------------+
        | ``customer_code``   | ``2``                |                      |
        +---------------------+----------------------+----------------------+
        | ``Rename Perfdata`` | ``customer_code``    | ``customer_code_02`` |
        +---------------------+----------------------+----------------------+
        |                     |                      |                      |
        +---------------------+----------------------+----------------------+
        | ``Delete Perfdata`` | ``customer_code``    |                      |
        +---------------------+----------------------+----------------------+
        | ``Print Perfdata``  |                      |                      |
        +---------------------+----------------------+----------------------+

.. warning::
    Executing two or more times the same :ref:`visual keyword <visual_keywords>` simply **overrides its current performance measure**, so loosing the previous one. *Rename Perfdata* **avoids the need to define a new visual** keyword with the same graphic elements to detect.


.. _system_keywords-performance_keywords-sum_perfdata:

Sum Perfdata
------------

    +------------------+------------------+---+---+------------------+-------------------------+
    | ``Sum Perfdata`` | ``<perfname 1>`` | . | . | ``<perfname n>`` | ``name=<new perfname>`` |
    +------------------+------------------+---+---+------------------+-------------------------+

    * Default arguments:

        +-----------------------------+------------------------------+
        | ``warning_threshold =None`` | ``critical_threshold =None`` |
        +-----------------------------+------------------------------+

    * Value types: ``warning_threshold=<seconds>``, ``critical_threshold=<seconds>``

Example:

    +------------------+-------------------+-------------------+-----------------------+
    | ``Sum Perfdata`` | ``login_step_01`` | ``login_step_02`` | ``name =login_steps`` |
    +------------------+-------------------+-------------------+-----------------------+

    +------------------+-------------+-------------+-----------------+--------------------------+-----------------------------+
    | ``Sum Perfdata`` | ``step_01`` | ``step_02`` | ``name =login`` | ``warning_threshold =5`` | ``critical_threshold =7.5`` |
    +------------------+-------------+-------------+-----------------+--------------------------+-----------------------------+

*Sum Perfdata* **sums the given performance measures in a new one**. At least, you have to set **two** ``<performance name>`` **to sum** in the ``<new performance name>``. It is also possible to **define warning and critical thresholds** of the new keyword.

.. note::
    At the end of the test, before :ref:`Print Perfdata <system_keywords-performance_keywords-print_perfdata>`, it could be the case to :ref:`delete the old partial keywords <system_keywords-performance_keywords-delete_perfdata>`.


.. _system_keywords-performance_keywords-add_perfdata_tag:

Add Perfdata Tag
----------------

    +----------------------+---------------+--------------+---------------+
    | ``Add Perfdata Tag`` | ``perf_name`` | ``tag_name`` | ``tag_value`` |
    +----------------------+---------------+--------------+---------------+

    * Value types: ``perf_name={<perf name>, all}``, ``tag_name=<tag name>``, ``tag_value=<tag value>``

Example:

    +----------------------+--------------------------------+--------------------------+----------------------+
    | ``Add Perfdata Tag`` | ``perf_name =ax12_home_ready`` | ``tag_name =aos_name``   | ``tag_value =bla01`` |
    +----------------------+--------------------------------+--------------------------+----------------------+

    +----------------------+--------------------------------+--------------------------+----------------------+
    | ``Add Perfdata Tag`` | ``perf_name =all``             | ``tag_name =id_session`` | ``tag_value =1``     |
    +----------------------+--------------------------------+--------------------------+----------------------+

*Add Perfdata Tag* **adds a custom tag to** a performance point or to all **performance points** of a test case. It could be useful for publishing performance in :ref:`NATS mode<system_keywords-performance_keywords-publish_perfdata-nats_mode>`.


.. _system_keywords-performance_keywords-add_perfdata_field:

Add Perfdata Field
------------------

    +------------------------+---------------+----------------+-----------------+
    | ``Add Perfdata Field`` | ``perf_name`` | ``field_name`` | ``field_value`` |
    +------------------------+---------------+----------------+-----------------+

    * Value types: ``perf_name={<perf name>, all}``, ``field_name=<field name>``, ``field_value=<field value>``

Example:

    +------------------------+--------------------------------+----------------------------+------------------------+
    | ``Add Perfdata Field`` | ``perf_name =ax12_home_ready`` | ``field_name =aos_name``   | ``field_value =bla01`` |
    +------------------------+--------------------------------+----------------------------+------------------------+

    +------------------------+--------------------------------+----------------------------+------------------------+
    | ``Add Perfdata Field`` | ``perf_name =all``             | ``field_name =id_session`` | ``field_value =1``     |
    +------------------------+--------------------------------+----------------------------+------------------------+

*Add Perfdata Field* **adds a custom field to** a performance point or to all **performance points** of a test case. It could be useful for publishing performance in :ref:`NATS mode<system_keywords-performance_keywords-publish_perfdata-nats_mode>`.


.. _system_keywords-performance_keywords-delete_perfdata:

Delete Perfdata
---------------

    +---------------------+----------+
    | ``Delete Perfdata`` | ``name`` |
    +---------------------+----------+

    * Value types: ``name=<perfname>``

Example:

    +---------------------+-------------------+
    | ``Delete Perfdata`` | ``login_step_01`` |
    +---------------------+-------------------+

*Delete Perfdata* **deletes an existing performance measure**. It is useful after :ref:`Rename Perfdata <system_keywords-performance_keywords-rename_perfdata>` or :ref:`Delete Perfdata <system_keywords-performance_keywords-delete_perfdata>` and before :ref:`Print Perfdata <system_keywords-performance_keywords-print_perfdata>` to clean the final test case outcome.


.. _system_keywords-timestamp_keywords:

Timestamp keywords
==================


.. _system_keywords-timestamp_keywords-check_date_today:

Check Date Today
----------------

    +----------------------+--------------------+
    | ``Check Date Today`` | ``scraped_string`` |
    +----------------------+--------------------+

    * Value types: ``scraped_string=<scraped string>``

Example:

    +-----------------------+---------------------+----------------------+-----------------------+
    | ``${scraped_string}`` | ``date_scraper``    |                      |                       |
    +-----------------------+---------------------+----------------------+-----------------------+
    | ``${sanity_check}``   | ``${scraped_date}`` | ``Check Date Today`` | ``${scraped_string}`` |
    +-----------------------+---------------------+----------------------+-----------------------+

*Check Date Today* **extract a date from a scraped string** that comes from a :ref:`visual scraper <visual_keywords-alyvix_scrapers>` and **check if that is today**. The **date format** has to be one of the following: ``dd/mm/yyyy``, ``dd/mm``, ``mm/dd/yyyy`` or ``mm/dd``.


.. _system_keywords-timestamp_keywords-check_hms_time_proximity:

Check Hms Time Proximity
------------------------

    +------------------------------+--------------------+
    | ``Check Hms Time Proximity`` | ``scraped_string`` |
    +------------------------------+--------------------+

    * Default values:

        +--------------------------+
        | ``proximity_minutes=60`` |
        +--------------------------+

    * Value types: ``scraped_string=<scraped string>``, ``proximity_minutes=<sanity minutes>``

Example:

    +--------------------+------------------------------+--------------------+
    | ``${scraped_hms}`` | ``hms_scraper``              |                    |
    +--------------------+------------------------------+--------------------+
    | ``${hms_check}``   | ``Check Hms Time Proximity`` | ``${scraped_hms}`` |
    +--------------------+------------------------------+--------------------+

    +--------------------+------------------------------+--------------------+---------+
    | ``${hms_check}``   | ``Check Hms Time Proximity`` | ``${scraped_hms}`` | ``180`` |
    +--------------------+------------------------------+--------------------+---------+

*Check Hms Time Proximity* **extract a time from a scraped string** that comes from a :ref:`visual scraper <visual_keywords-alyvix_scrapers>` and **check if that is near the current time**. The ``proximity_minutes`` argument can set the **allowed amount of misalignment minutes**, they are 60 by default. The **time format** has to be ``hh:mm:ss``.


.. _system_keywords-network_keywords:

Network keywords
================


.. _system_keywords-network_keywords-get_mstsc_hostname:

Get Mstsc Hostname
------------------

    +------------------------+-------------------+
    | ``Get Mstsc Hostname`` | ``customer_name`` |
    +------------------------+-------------------+

    * Default values:

        +-------------------------------+
        | ``path_json=<testcase path>`` |
        +-------------------------------+

    * Value types: ``customer_name=<prefix ip hostname map>``

Example:

    +-----------------------+------------------------+---------------+-----------------------+
    | ``${mstsc_hostname}`` | ``Get Mstsc Hostname`` | ``probename`` |                       |
    +-----------------------+------------------------+---------------+-----------------------+
    | ``Add Perfdata Tag``  | ``desktop_ready``      | ``hostname``  | ``${mstsc_hostname}`` |
    +-----------------------+------------------------+---------------+-----------------------+

    +-----------------------+------------------------+---------------+-----------------------------------------------------------------------------------+
    | ``${mstsc_hostname}`` | ``Get Mstsc Hostname`` | ``probename`` | ``C:\\Python27\\ Lib\\ site-packages\\ alyvix\\ robotproxy\\ alyvix_testcases\\`` |
    +-----------------------+------------------------+---------------+-----------------------------------------------------------------------------------+

.. warning::
  Type the **folder path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path ip hostname map>\\``).

*Get Mstsc Hostname* **provides the** ``mstsc`` **hostname of an ongoing RDP connection**. :download:`probename_ip_hostname_map.json <./probename_ip_hostname_map.json>` is the **needed map between the desired names and the IP addresses of possible RDP servers**.

The ``probename`` **filename suffix**, that can be changed (e.g. ``customername_ip_hostname_map.json``), is the **keyword argument to use the map** (e.g. ``${mstsc_hostname} |`` ``Get Mstsc Hostname`` ``| customername``). The file has to be saved in a given folder, which can be passed as the second keyword argument: the test case path (e.g. ``C:\Python27\ Lib\ site-packages\ alyvix\ robotproxy\ alyvix_testcases\``) is already set by default.

Define the map as a list of ip and name associations ``"<ip rdp host>": "<name rdp host>"`` as follows:

    .. code-block:: json

        {
            "127.0.0.1": "hostname_1",
            "127.0.0.2": "hostname_2"
        }


.. _system_keywords-network_keywords-get_aos_id:

Get Aos Id
----------

    +----------------+--------------------+-------------------+
    | ``Get Aos Id`` | ``scraped_string`` | ``customer_name`` |
    +----------------+--------------------+-------------------+

    * Default values:

        +-------------------------------+
        | ``path_json=<testcase path>`` |
        +-------------------------------+

    * Value types: ``scraped_string=<scraped string>``, ``customer_name=<prefix customer settings>``.

Example:

    +----------------------+--------------+----------------+--------------+---------------+
    | ``${scrap}``         | ``scraper``  |                |              |               |
    +----------------------+--------------+----------------+--------------+---------------+
    | ``${aos}``           | ``${sid}``   | ``Get Aos Id`` | ``${scrap}`` | ``probename`` |
    +----------------------+--------------+----------------+--------------+---------------+
    | ``Add Perfdata Tag`` | ``ax_ready`` | ``aos_name``   | ``${aos}``   |               |
    +----------------------+--------------+----------------+--------------+---------------+
    | ``Add Perfdata Tag`` | ``ax_ready`` | ``session_id`` | ``${sid}``   |               |
    +----------------------+--------------+----------------+--------------+---------------+

    +----------------+--------------+---------------+-----------------------------+
    | ``Get Aos Id`` | ``${scrap}`` | ``probename`` | ``C:\\ alyvix_testcases\\`` |
    +----------------+--------------+---------------+-----------------------------+

.. warning::
  Type the **folder path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path customer settings>\\``).

*Get Aos Id* **extract and map a name** (e.g. `AOS <https://en.wikipedia.org/wiki/Application_server>`_ name) **and a number** (e.g. session ID) **from a scraped string** that comes from a :ref:`visual scraper <visual_keywords-alyvix_scrapers>`. The AOS map has to be defined in a JSON file like :download:`probename_customer_settings.json <./probename_customer_settings.json>`.

    .. image:: pictures/ax_aos_id_hompage_gui.png

..

    .. image:: pictures/ax_aos_id_scraped_title.png

The ``probename`` **filename suffix**, that can be changed (e.g. ``customername_customer_settings.json``), is the **keyword argument to use the map** (e.g. ``${aos_name} |`` ``${session_id} |`` ``Get Aos Id`` ``| ${scraped_string}`` ``| customername``). The file has to be saved in a given folder, which can be passed as the second keyword argument: the test case path (e.g. ``C:\Python27\ Lib\ site-packages\ alyvix\ robotproxy\ alyvix_testcases\``) is already set by default.

In the setting file, define ``"ax_title_marks"`` as the list of **text anchors** between which extracting the name and the number; define ``"aos_names"`` as the list of **text labels** on which mapping the extracted name:

    .. code-block:: json

        {
            "ax_title_marks": {
                "aos_stop": ": Session",
                "aos_start": "Inc. [",
                "id_start": "ID - ",
                "id_stop": "] - ["
            },
            "aos_names": [
                "TEST1AOS_1",
                "TEST1AOS_2",
                "TEST2AOS_1",
                "TEST2AOS_2"
            ]
        }


.. _system_keywords-screenshot_keywords:

Screenshot keywords
===================


.. _system_keywords-screenshot_keywords-alyvix_screenshot:

Alyvix Screenshot
-----------------

    +-----------------------+------------------+
    | ``Alyvix Screenshot`` | ``filename_arg`` |
    +-----------------------+------------------+

    * Value types: ``filename_arg=<screenshot filename>{.png, .jpg}``.

Example:

    +-----------------------+----------------------+
    | ``Alyvix Screenshot`` | ``login_screen.jpg`` |
    +-----------------------+----------------------+

*Alyvix Screenshot* **grabs a screenshot and saves it into the output folder**, which can be specified as an argument ``--outputdir <output folder path>`` (e.g. ``--outputdir "C:\alyvix_reports\ login_testcase"``) of the Alyvix :ref:`test case script <commandline_output>`. By default the extension of the screenshot file is ``.png``, but it is also possible to specify ``.jpg`` as the image compression.


.. _system_keywords-debug_keywords:

Debug keywords
==============


.. _system_keywords-debug_keywords-alyvix_config:

Alyvix Config
-------------

    +-------------------+-------------------+
    | ``Alyvix Config`` | ``full_filename`` |
    +-------------------+-------------------+

    * Value types: ``full_filename=<config.xml file path>``.

Example:

    +-------------------+--------------------------------------+
    | ``Alyvix Config`` | ``C:\\alyvix_logbooks\\ config.xml`` |
    +-------------------+--------------------------------------+

.. warning::
  Type the **folder path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path to>\\ config.xml``).

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

Edit ``config.xml`` to enable the Alyvix **debugging mode** (``<log><enable>True``) and set in which folder storing the **detection screenshots** of Alyvix objects (``<log><home>C:\<path to folder>``). It is also possible to set the **time periods of the frame grabber** ``<finder><finder_thread_interval>0.5`` (0.5s by default) and **of the object detector** ``<finder><check_diff_interval>0.1`` (0.1s by default).

.. note::
  It is recommended to **leave the default values** (i.e. ``0.5`` for the detector and ``0.1`` for the grabber), in order to avoid overloading the hardware. But you can **increase the measurement accuracy** decreasing the detector period ``<finder><finder_thread_interval>`` and you can **increase the measurement precision** decreasing the grabber period ``<finder><check_diff_interval>``.


.. _system_keywords-debug_keywords-set_alyvix_info:

Set Alyvix Info
---------------

    +---------------------+----------+-----------+
    | ``Set Alyvix Info`` | ``name`` | ``value`` |
    +---------------------+----------+-----------+

    * Value types: ``name={CHECK DIFF INTERVAL, FINDER THREAD INTERVAL, CHECK DIFF INTERVAL DISAPPEAR, FINDER THREAD INTERVAL DISAPPEAR, ACTIONS DELAY, channel}``, ``value={<milliseconds>, r, g, b}``.

CHECK DIFF INTERVAL, FINDER THREAD INTERVAL, CHECK DIFF INTERVAL DISAPPEAR, FINDER THREAD INTERVAL DISAPPEAR, ACTIONS DELAY, channel``

Example:

    +---------------------+---------------------------------------------+-----------------+
    | ``Set Alyvix Info`` | ``name = CHECK DIFF INTERVAL``              | ``value = 0.1`` |
    +---------------------+---------------------------------------------+-----------------+
    | ``Set Alyvix Info`` | ``name = FINDER THREAD INTERVAL``           | ``value = 0.5`` |
    +---------------------+---------------------------------------------+-----------------+
    | ``Set Alyvix Info`` | ``name = CHECK DIFF INTERVAL DISAPPEAR``    | ``value = 0.1`` |
    +---------------------+---------------------------------------------+-----------------+
    | ``Set Alyvix Info`` | ``name = FINDER THREAD INTERVAL DISAPPEAR`` | ``value = 0.5`` |
    +---------------------+---------------------------------------------+-----------------+
    | ``Set Alyvix Info`` | ``name = ACTIONS DELAY``                    | ``value = 0.5`` |
    +---------------------+---------------------------------------------+-----------------+
    | ``Set Alyvix Info`` | ``name = channel``                          | ``value = r``   |
    +---------------------+---------------------------------------------+-----------------+

*Set Alyvix Info* **sets values of the Alyvix engine settings**. *Set Alyvix Info* acts from its call point until the end of the test case (or until another setup).

*Set Alyvix Info* can set the following properties:

    * ``CHECK DIFF INTERVAL`` redefines the **amount of seconds** (e.g. ``0.1``) that **Alyvix waits before grabbing a new screen frame** (on which it tries to detect the appearance of graphic elements); you can consider this setting as the **measurement precision of the graphic appearance detection**; the default value is ``0.1``;

    * ``CHECK DIFF INTERVAL DISAPPEAR`` redefines the **amount of seconds** (e.g. ``0.1``) that **Alyvix waits before grabbing a new screen frame** (on which it tries to detect the disappearance of graphic elements); you can consider this setting as the **measurement precision of the graphic disappearance detection**; the default value is ``0.1``;

    * ``FINDER THREAD INTERVAL`` redefines the **amount of seconds** (e.g. ``0.5``) that **Alyvix takes between attempts to detect the appearance of graphic elements**; you can consider this setting as the **measurement accuracy of the graphic appearance detection**; the default value is ``0.5``;

    * ``FINDER THREAD INTERVAL DISAPPEAR`` redefines the **amount of seconds** (e.g. ``0.5``) that **Alyvix takes between attempts to detect the disappearance of graphic elements**; you can consider this setting as the **measurement accuracy of the graphic disappearance detection**; the default value is ``0.5``;

    * ``ACTIONS DELAY`` to redefine the **amount of seconds** (e.g. ``0.5``) that **Alyvix takes after each interaction step**; the default value is ``0.5``.

    * ``channel`` to **select just one single color channel** (``r`` as red, ``g`` as green or ``b`` as blue) and **cutoff the other two**; the default value is ``all``.
