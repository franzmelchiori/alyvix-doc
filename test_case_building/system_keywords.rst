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
    | ``Create Process`` | ``C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe`` | ``https://www.alyvix.com`` | ``–incognito`` |
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

*Kill Process* **kills a process** providing its executable filename. It could be useful to fetch the list of the ongoing programs (at some point) having a look at *Windows Task Manager*, in the *Detail* tab.

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

    * Optional arguments: ``timeout=<seconds>``, ``exception={True, False}``.

    * Default values: ``timeout=60``, ``exception=True``.

Examples:

    +-----------------+-----------------------------------+
    | ``Wait Window`` | ``synthetic.*monitoring.*alyvix`` |
    +-----------------+-----------------------------------+

    +-----------------+-----------------------------------+----------------+--------------------+
    | ``Wait Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=10`` | ``exception=True`` |
    +-----------------+-----------------------------------+----------------+--------------------+

*Wait Window* **waits until a window is running** and can be activated (e.g. from the taskbar). The keyword waits the given timeout of seconds and it waits for a window with a title name that fits the given regular expression. When the timeout is expired without having found a window with a proper title, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.


.. _system_keywords-window_keywords-maximize_window:

Maximize Window
---------------

    +---------------------+---------------------------+-----------------------+-----------------------------+
    | ``Maximize Window`` | ``<window_title_regexp>`` | ``timeout=<seconds>`` | ``exception={True, False}`` |
    +---------------------+---------------------------+-----------------------+-----------------------------+

    * Optional arguments: ``timeout=<seconds>``, ``exception={True, False}``.

    * Default values: ``timeout=60``, ``exception=True``.

Examples:

    +---------------------+-----------------------------------+
    | ``Maximize Window`` | ``synthetic.*monitoring.*alyvix`` |
    +---------------------+-----------------------------------+

    +---------------------+-----------------------------------+----------------+--------------------+
    | ``Maximize Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=10`` | ``exception=True`` |
    +---------------------+-----------------------------------+----------------+--------------------+

*Maximize Window* **waits and maximizes the size of a window**. The keyword waits the given timeout of seconds and it maximizes a window with a title name that fits the given regular expression. When the timeout is expired without having found a window with a proper title, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.

.. note::
    It is a best practice to maximize the window on which the rest of test case will work, because it can **limit the "graphical noise"** coming from the rest of the GUI on screen. This can optimize the detection of the Alyvix visual keywords just on the interested application window.


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

*Show Window* **brings in foreground a window** (without resizing it) with a title name that fits the given regular expression. This keyword has an immediate timeout and no exception.



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

*Check Window* **checks the existence of a window** (in background or in foreground) with a title name that fits the given regular expression, returning ``True`` or ``False`` for further decision or logging steps. This keyword has an immediate timeout and no exception.


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

*Close Window* **closes a window** (in background or in foreground) with a title name that fits the given regular expression. This keyword has an immediate timeout and no exception.


.. _system_keywords-window_keywords-wait_window_close:

Wait Window Close
-----------------

    +-----------------------+---------------------------+-----------------------+-----------------------------+
    | ``Wait Window Close`` | ``<window_title_regexp>`` | ``timeout=<seconds>`` | ``exception={True, False}`` |
    +-----------------------+---------------------------+-----------------------+-----------------------------+

    * Optional arguments: ``timeout=<seconds>``, ``exception={True, False}``.

    * Default values: ``timeout=60``, ``exception=True``.

Example:

    +-----------------------+-----------------------------------+
    | ``Wait Window Close`` | ``synthetic.*monitoring.*alyvix`` |
    +-----------------------+-----------------------------------+

    +-----------------------+-----------------------------------+----------------+--------------------+
    | ``Wait Window Close`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=30`` | ``exception=True`` |
    +-----------------------+-----------------------------------+----------------+--------------------+

*Wait Window Close* **waits until a window is closed**. The keyword waits the given timeout of seconds and it waits for the disappearance of a window with a title name that fits the given regular expression. When the timeout is expired without having found a window with a proper title, then the test case breaks if the exception is ``True``, otherwise (in case the exception is ``False``) the test case continues its execution with the next command.


.. _system_keywords-io_keywords:

I/O keywords
============


.. _system_keywords-io_keywords-send_keys:

Send Keys
---------

    +---------------+------------+-----------------------------+
    | ``Send Keys`` | ``<keys>`` | ``encrypted={True, False}`` |
    +---------------+------------+-----------------------------+

    * Optional arguments: ``encrypted={True, False}``.

    * Default values: ``encrypted=False``.

    * Key syntax:

    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Enter}`                              | **ENTER** key                                                                                       |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Space}`                              | **SPACE** key (only needed at the beginning or the end of the string)                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Tab}`                                | **TAB** key                                                                                         |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Shift}`                              | **SHIFT** key; :literal:`{LShift}` for Left SHIFT key; :literal:`{RShift}` for Right SHIFT key      |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Shift Down}` - :literal:`{Shift Up}` | :literal:`{Shift Down}` holds the **SHIFT** key down until :literal:`{Shift Up}` is sent            |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Ctrl}`                               | **CONTROL** key; :literal:`{LCtrl}` for Left CONTROL key; :literal:`{RCtrl}` for Right CONTROL key  |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Ctrl Down}` - :literal:`{Ctrl Up}`   | :literal:`{Ctrl Down}` holds the **CONTROL** key down until :literal:`{Ctrl Up}` is sent            |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Alt}`                                | **ALT** key; :literal:`{LAlt}` for Left ALT key; :literal:`{RAlt}` for Right ALT key                |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Alt Down}` - :literal:`{Alt Up}`     | :literal:`{Alt Down}` holds the **ALT** key down until :literal:`{Alt Up}` is sent                  |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{~}`                                  | **~**                                                                                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{!}`                                  | **!**                                                                                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{#}`                                  | **#**                                                                                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`%`                                    | **%**                                                                                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{^}`                                  | **^**                                                                                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{+}`                                  | **\+**                                                                                              |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`\``                                   | **\`**                                                                                              |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{{}`                                  | **{**                                                                                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{}}`                                  | **}**                                                                                               |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Backspace}`                          | **Backspace** key                                                                                   |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Del}`                                | **Delete** key                                                                                      |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Esc}`                                | **ESCAPE** key                                                                                      |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{F1}` - :literal:`{F24}`              | **Function** keys                                                                                   |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Up}`                                 | **Up-arrow** key                                                                                    |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Down}`                               | **Down-arrow** key                                                                                  |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Left}`                               | **Left-arrow** key                                                                                  |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Right}`                              | **Right-arrow** key                                                                                 |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{Home}`                               | **Home** key                                                                                        |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{End}`                                | **End** key                                                                                         |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{PgUp}`                               | **Page-up** key                                                                                     |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{PgDn}`                               | **Page-down** key                                                                                   |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+
    | :literal:`{PgDn}`                               | **Page-down** key                                                                                   |
    +-------------------------------------------------+-----------------------------------------------------------------------------------------------------+

Example:

    +---------------+----------------+---------------------+
    | ``Send Keys`` | ``admin{Tab}`` |                     |
    +---------------+----------------+---------------------+
    | ``Send Keys`` | ``admin``      | ``encrypted=False`` |
    +---------------+----------------+---------------------+
    | ``Send Keys`` | ``{Enter}``    |                     |
    +---------------+----------------+---------------------+

    +---------------+----------------------------+
    | ``Send Keys`` | ``{Alt Down}{F4}{Alt Up}`` |
    +---------------+----------------------------+

*Send Keys* **types a sequence of keystrokes** to the active window where the focus is: regular characters (letters and numbers) can be stated as they are, while special keys have to be enclosed in braces (have a look at the table of the key syntax, e.g. ``{enter}``). The encrypted option can be activated (i.e. ``encrypted=True``) in case the string of keystrokes has been encrypted using the Alyvix :ref:`encryption tool <encryption_tool>`.


.. _system_keywords-io_keywords-mouse_scroll:

Mouse Scroll
------------

    +------------------+---------------------+--------------------------+
    | ``Mouse Scroll`` | ``steps=<scrolls>`` | ``direction={down, up}`` |
    +------------------+---------------------+--------------------------+

    * Optional arguments: ``steps=<scrolls>``, ``direction={down, up}``.

    * Default values: ``steps=2``, ``direction=up``.

Example:

    +------------------+-------------+--------------------+
    | ``Mouse Scroll`` | ``steps=3`` | ``direction=down`` |
    +------------------+-------------+--------------------+

*Mouse Scroll* **scrolls the active window**. The keyword scrolls the windows of the given steps, up or down and where the focus is.

.. note::
    *Mouse Scroll* is useful for scanning windows (e.g. website in a browser) searching for graphic elements defined in :ref:`visual keywords <visual_keywords>`.


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

*Mouse Move* **moves the mouse pointer** to the given horizontal and vertical pixel coordinates within your screen.

.. note::
    Keep in mind that the positive verse of the horizontal screen coordinate x is from left to right. The positive verse of the vertical screen coordinate y is from top to bottom. So that, the origin of screen axes is at the point ``x=0`` ``y=0`` in the top-left corner. Sometimes leaving the mouse pointer in a certain position after a transaction can cause unintended interactions following.


.. _system_keywords-performance_keywords:

Performance keywords
====================


.. _system_keywords-performance_keywords-add_perfdata:

Add Perfdata
------------

    +------------------+------------------------+---------------------+---------------------------------+----------------------------------+------------------------+-----------------------------+
    | ``Add Perfdata`` | ``<performance_name>`` | ``value=<seconds>`` | ``warning_threshold=<seconds>`` | ``critical_threshold=<seconds>`` | ``state={0, 1, 2, 3}`` | ``timestamp={True, False}`` |
    +------------------+------------------------+---------------------+---------------------------------+----------------------------------+------------------------+-----------------------------+

    * Optional arguments: ``value=<seconds>``, ``warning_threshold=<seconds>``, ``critical_threshold=<seconds>``, ``state={0, 1, 2, 3}``.

    * Default values: ``value=None``, ``warning_threshold=None``, ``critical_threshold=None``, ``state=2``, ``timestamp=False``.

Example:

    +------------------+------------------+
    | ``Add Perfdata`` | ``citrix_login`` |
    +------------------+------------------+

    +------------------+------------------+-------------+-------------------------+--------------------------+-------------+--------------------+
    | ``Add Perfdata`` | ``dummy_perf``   | ``value=1`` | ``warning_threshold=3`` | ``critical_threshold=5`` | ``state=3`` | ``timestamp=True`` |
    +------------------+------------------+-------------+-------------------------+--------------------------+-------------+--------------------+

*Add Perfdata* **declares a performance variable**, which could have the name of an Alyvix visual keyword: when a visual keyword finishes to execute, it fills the performance variable with the measurement and the other data (thresholds, state and eventually timestamp).

.. note::
    The ``state`` argument set the default ``errorlevel`` code that returns from broken test cases. Those codes have the following meanings:

        * ``0`` **OK**
        * ``1`` **WARNING**
        * ``2`` **CRITICAL**
        * ``3`` **UNKNOWN**.

.. warning::
    It is convenient to **declare all performance variables at the beginning of test cases**: in this way we can know at which point the test case eventually breaks. If a performance variable is not filled at the end of a test case (maybe because the test case breaks before or at that point) the keyword state returns ``2`` **CRITICAL** as default.


.. _system_keywords-performance_keywords-print_perfdata:

Print Perfdata
--------------

    +--------------------+----------------------+--------------------------------+
    | ``Print Perfdata`` | ``message=<string>`` | ``print_output={True, False}`` |
    +--------------------+----------------------+--------------------------------+

    * Optional arguments: ``message=<string>``, ``print_output={True, False}``.

    * Default values: ``message=None``, ``print_output=True``.

Example:

    +--------------------+
    | ``Print Perfdata`` |
    +--------------------+

*Print Perfdata* **prints all the performance variables** declared (and filled, but not declared) to a test case. By default (``print_output=True``), a message is printed out at the end of a test case execution to describe the overall state and eventually with the name of the last performance variable that has been measured and filled before a failure.


.. _system_keywords-performance_keywords-store_perfdata:

Store Perfdata
--------------

    +--------------------+----------------------------+
    | ``Store Perfdata`` | ``dbname=<database_path>`` |
    +--------------------+----------------------------+

    * Optional arguments: ``dbname=<database_path>``.

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

*Store Perfdata* **saves the output data of a test case in its SQLite database** file. all the data about the execution of a test case. New data are added to past data that comes to previous execution of the test case: in this way, Alyvix probes can track test case outputs during the time.


.. _system_keywords-performance_keywords-publish_perfdata:

Publish Perfdata
----------------

  +----------------------+---------------------------+-------------------------------------------+-----------------------------------------+--------------------------------------------------+-------------------------------------------------------+-------------------------------------------------+
  | ``Publish Perfdata`` | ``type = {csv, perfmon}`` | ``start_date = <yyyy-mm-dd hh:mm>`` [csv] | ``end_date = <yyyy-mm-dd hh:mm>`` [csv] | ``filename = <path_to_testcase_csv_file>`` [csv] | ``testcase_name = <testcase_name_to_list>`` [perfmon] | ``max_age = <database_data_max_age>`` [perfmon] |
  +----------------------+---------------------------+-------------------------------------------+-----------------------------------------+--------------------------------------------------+-------------------------------------------------------+-------------------------------------------------+

    Publishes test case performances in a CSV file or in Windows Performance Monitor. csv type takes mandatory start and end dates in the following format yyyy-mm-dd hh:mm (e.g. 2016-07-29 09:00) and an optional path to the CSV file that will be written. perfmon type takes an optional test case name to list in Windows Performance Monitor. It also takes an optional max_age amount of hours as maximum range of past hours for data to consider. Default value: max_age=24. If Alyvix was installed correctly, through a command prompt run as administrator, its Windows service called Alyvix Wpm Service should run in background. Therefore, Alyvix can publish performances in WPM out-of-the-box: Alyvix- will be available in the list of WPM metrics to add.

  Example:

  +----------------------+------------------+---------------------------------+-------------------------------+----------------------------------------------------+
  | ``Publish Perfdata`` | ``type=csv``     | ``start_date=2016-02-01 00:01`` | ``end_date=2016-08-04 23:59`` | ``filename=C:\\alyvix_testcases\\citrix_word.csv`` |
  +----------------------+------------------+---------------------------------+-------------------------------+----------------------------------------------------+
  | ``Publish Perfdata`` | ``type=perfmon`` | ``testcase_name=citrix_word``   | ``max_age=24``                |                                                    |
  +----------------------+------------------+---------------------------------+-------------------------------+----------------------------------------------------+


.. _system_keywords-performance_keywords-add_perfdata_tag:

Add Perfdata Tag
----------------

bla


.. _system_keywords-performance_keywords-rename_perfdata:

Rename Perfdata
---------------

  +---------------------+----------------------------+----------------------------+-------------------------+--------------------------+
  | ``Rename Perfdata`` | ``<old_performance_name>`` | ``<new_performance_name>`` | ``<warning_threshold>`` | ``<critical_threshold>`` |
  +---------------------+----------------------------+----------------------------+-------------------------+--------------------------+

    Copies the values of an existing keyword (measured performance, set thresholds) under a new name. That is useful in order to reuse multiple times the same keyword with different arguments (e.g. object finder searching for the same image as main component and for a different text string as sub component passed as an argument) keeping track of output performance at each step renaming its name every time. It is also possible to redefine warning and critical thresholds. Default values: without changes, warning and critical thresholds are the ones within the original keyword definition.

  Example:

  +---------------------+------------------------+-------------------+--------+---------+
  | ``Rename Perfdata`` | ``login_generic_step`` | ``login_step_01`` | ``5``  | ``7.5`` |
  +---------------------+------------------------+-------------------+--------+---------+
  | ``Rename Perfdata`` | ``login_generic_step`` | ``login_step_02`` | ``10`` | ``15``  |
  +---------------------+------------------------+-------------------+--------+---------+
  | ``Rename Perfdata`` | ``login_generic_step`` | ``login_step_03`` |        |         |
  +---------------------+------------------------+-------------------+--------+---------+


.. _system_keywords-performance_keywords-sum_perfdata:

Sum Perfdata
------------

  +------------------+--------------------------+--------+--------------------------+---------------------------------+----------------------------+
  | ``Sum Perfdata`` | ``<performance_name_1>`` | ``..`` | ``<performance_name_n>`` | ``name=<new_performance_name>`` | ``delete_perfdata=<bool>`` |
  +------------------+--------------------------+--------+--------------------------+---------------------------------+----------------------------+

    Sums the given performance variables into a new one. Default values: delete_perfdata=false.

  Example:

  +------------------+-------------------+-------------------+----------------------+--------------------------+
  | ``Sum Perfdata`` | ``login_step_01`` | ``login_step_02`` | ``name=login_steps`` | ``delete_perfdata=true`` |
  +------------------+-------------------+-------------------+----------------------+--------------------------+


.. _system_keywords-performance_keywords-get_perfdata:

Get Perfdata
------------

bla


.. _system_keywords-performance_keywords-delete_perfdata:

Delete Perfdata
---------------s

  +---------------------+------------------------+
  | ``Delete Perfdata`` | ``<performance_name>`` |
  +---------------------+------------------------+

    Deletes an existing performance. That is useful, for example, in case of renamed performances: one can reuse multiple times the same Alyvix keyword, retaining every time its new performance renaming it and at the end the test, before printing the output, deleting it.

  Example:

  +---------------------+------------------------+
  | ``Delete Perfdata`` | ``login_generic_step`` |
  +---------------------+------------------------+


.. _system_keywords-screenshot_keywords:

Screenshot keywords
===================


.. _system_keywords-screenshot_keywords-alyvix_screenshot:

Alyvix Screenshot
-----------------

    +-----------------------+----------------+
    | ``Alyvix Screenshot`` | ``<filename>`` |
    +-----------------------+----------------+

Example:

    +-----------------------+---------------+
    | ``Alyvix Screenshot`` | ``login.jpg`` |
    +-----------------------+---------------+

Grabs a screenshot and saves it into the output folder, which can be specified as an argument (–outputdir <path_to_folder>) of the alyvix_pybot.bat through command prompt. By default the extension of the file is .png, but it is possible to specify a .jpg as the extension after the filename.


.. _system_keywords-screenshot_keywords-overwrite_alyvix_screen:

Overwrite Alyvix Screen
-----------------------

bla


.. _system_keywords-debug_keywords:

Debug keywords
==============


.. _system_keywords-debug_keywords-alyvix_config:

Alyvix Config
-------------

    +-------------------+----------------------------+
    | ``Alyvix Config`` | ``<config.xml_file_path>`` |
    +-------------------+----------------------------+

Example:

    +-------------------+-------------------------------------+
    | ``Alyvix Config`` | ``C:\\alyvix_logbooks\\config.xml`` |
    +-------------------+-------------------------------------+

.. warning::
  Type the **folder path with double backslashes** ``\\`` instead of single backslashes ``\`` (e.g. ``C:\\<path_to_folder>``).

*Alyvix Config* links the :download:`config.xml <./config.xml>` file to get some Alyvix **custom settings**.

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

Edit ``config.xml`` to enable the Alyvix **debugging mode** (``<log><enable>True``) and set in which folder storing the screenshots of detected and failed Alyvix objects (``<log><home>C:\<path_to_folder>``).

It is also possible to set the time periods of the frame grabber ``<finder><finder_thread_interval>0.5`` (0.5s is the default value) and of the object detector ``<finder><check_diff_interval>0.1`` (0.1s is the default value).

.. note::
  It is recommended to leave the default values (i.e. ``0.5`` for the detector and ``0.1`` for the grabber), in order to avoid overloading the hardware. But you can **increase the measurement accuracy** decreasing the detector period ``<finder><finder_thread_interval>`` and you can **increase the measurement precision** decreasing the grabber period ``<finder><check_diff_interval>``.


.. _system_keywords-debug_keywords-set_alyvix_info:

Set Alyvix Info
---------------

    +---------------------+--------------------+---------------------+
    | ``Set Alyvix Info`` | ``<setting_name>`` | ``<setting_value>`` |
    +---------------------+--------------------+---------------------+

Example:

    +---------------------+--------------------------------------+------------+
    | ``Set Alyvix Info`` | ``CHECK DIFF INTERVAL``              | ``${0.1}`` |
    +---------------------+--------------------------------------+------------+
    | ``Set Alyvix Info`` | ``FINDER THREAD INTERVAL``           | ``${0.5}`` |
    +---------------------+--------------------------------------+------------+
    | ``Set Alyvix Info`` | ``CHECK DIFF INTERVAL DISAPPEAR``    | ``${0.1}`` |
    +---------------------+--------------------------------------+------------+
    | ``Set Alyvix Info`` | ``FINDER THREAD INTERVAL DISAPPEAR`` | ``${0.5}`` |
    +---------------------+--------------------------------------+------------+
    | ``Set Alyvix Info`` | ``ACTIONS DELAY``                    | ``${0.5}`` |
    +---------------------+--------------------------------------+------------+

.. warning::
    Type the **setting values between** ``${`` **and** ``}`` (e.g. ``${0.25}``); they are intended as **values in milliseconds**.

*Set Alyvix Info* sets values related to the Alyvix **engine settings**. *Set Alyvix Info* acts from its call point to the end of the test case (or to a new call).

*Set Alyvix Info* can set the following properties:

    * ``CHECK DIFF INTERVAL`` redefines the amount of seconds (e.g. ``${0.1}``) that Alyvix waits before grabbing a new screen frame (on which it tries to detect the appearance of graphic elements); you can consider this setting as the measurement precision of the graphic appearance detection; the default value is ``0.1``;

    * ``CHECK DIFF INTERVAL DISAPPEAR`` redefines the amount of seconds (e.g. ``${0.1}``) that Alyvix waits before grabbing a new screen frame (on which it tries to detect the disappearance of graphic elements); you can consider this setting as the measurement precision of the graphic disappearance detection; the default value is ``0.1``;

    * ``FINDER THREAD INTERVAL`` redefines the amount of seconds (e.g. ``${0.5}``) that Alyvix takes between attempts to detect the appearance of graphic elements; you can consider this setting as the measurement accuracy of the graphic appearance detection; the default value is ``0.5``;

    * ``FINDER THREAD INTERVAL DISAPPEAR`` redefines the amount of seconds (e.g. ``${0.5}``) that Alyvix takes between attempts to detect the disappearance of graphic elements; you can consider this setting as the measurement accuracy of the graphic disappearance detection; the default value is ``0.5``;

    * ``ACTIONS DELAY`` to redefine the amount of seconds (e.g. ``${0.5}``) that Alyvix takes after each interaction step; the default value is ``2``.
