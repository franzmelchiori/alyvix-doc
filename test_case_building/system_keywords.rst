.. _system_keywords:

***************
System keywords
***************


.. _system_keywords-debug_keywords:

Debug keywords
==============


.. _system_keywords-debug_keywords-alyvix_config:

Alyvix Config
-------------

  +-------------------+----------------------------+
  | ``Alyvix Config`` | ``<config.xml_file_path>`` |
  +-------------------+----------------------------+

    Points to the :download:`config.xml <./config.xml>` file with some Alyvix settings.

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

    Edit ``config.xml`` to enable the Alyvix debugging mode ``<log><enable>True`` and set in which folder storing the screenshots of detected and failed Alyvix objects ``<log><home>C:\<path_to_folder>``.

    It is also possible to set the time periods of the frame grabber ``<finder><finder_thread_interval>0.5`` (0.5s is the default value) and of the object detector ``<finder><check_diff_interval>0.1`` (0.1s is the default value), but is recommended to leave default values, in order to avoid overloading the hardware.

  Example:

  +-------------------+-------------------------------------+
  | ``Alyvix Config`` | ``C:\\alyvix_logbooks\\config.xml`` |
  +-------------------+-------------------------------------+


.. _system_keywords-debug_keywords-set_alyvix_info:

Set Alyvix Info
---------------

  +---------------------+--------------------+---------------------+
  | ``Set Alyvix Info`` | ``<setting_name>`` | ``<setting_value>`` |
  +---------------------+--------------------+---------------------+

    Sets values related to Alyvix engine settings, from the call point to the test end (or to a new setup). CHECK DIFF INTERVAL [DISAPPEAR] redefines the amount of seconds (e.g. ${0.1}) Alyvix takes before grabbing the next screen frame, where it tries to detect the [dis]appearance of graphics (measurement precision of the graphics [dis]appearance detection). FINDER THREAD INTERVAL [DISAPPEAR] redefines the amount of seconds Alyvix takes between attempts to detect the [dis]appearance of graphics (measurement accuracy of the graphics [dis]appearance detection). ACTIONS DELAY to redefine the amount of seconds Alyvix takes at each interaction step (the default value is 2).

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


.. _system_keywords-process_keywords:

Process keywords
================


.. _system_keywords-debug_keywords-create_process:

Create Process
--------------

  +--------------------+-----------------------------------+-------------------------------+----+-----------------+
  | ``Create Process`` | ``<application_executable_path>`` | ``<application_arguments_1>`` | .. | ``<app_arg_n>`` |
  +--------------------+-----------------------------------+-------------------------------+----+-----------------+

    Runs the executable file (reachable to a given path) of an application with its optional arguments. It is useful, for example, to run a browser (e.g. Internet Explorer, Chrome) with an address to point and eventually the option for private browsing.

  Example:

  +--------------------+----------------------------------------------------------------------+----------------------------+----------------+
  | ``Create Process`` | ``C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe`` | ``https://www.alyvix.com`` | ``–incognito`` |
  +--------------------+----------------------------------------------------------------------+----------------------------+----------------+


.. _system_keywords-debug_keywords-kill_process:

Kill Process
------------

  +------------------+---------------------------+
  | ``Kill Process`` | ``<executable_filename>`` |
  +------------------+---------------------------+

    Kills an application providing its executable filename. It is possible to fetch a list of the ongoing programs having a look at Windows Task Manager, under the Detail tab.

      .. image:: pictures/task_manager.png

  Example:

  +------------------+----------------+
  | ``Kill Process`` | ``chrome.exe`` |
  +------------------+----------------+


.. _system_keywords-window_keywords:

Window keywords
===============


.. _system_keywords-window_keywords-wait_window:

Wait Window
-----------

  +-----------------+--------------------------+-------------------------+------------------------+
  | ``Wait Window`` | ``<window_title_regex>`` | ``timeout = <seconds>`` | ``exception = <bool>`` |
  +-----------------+--------------------------+-------------------------+------------------------+

    Waits the timeout amount of seconds until a window, with a title name that fits the inserted regular expression, is running and can be activated (e.g. from the taskbar). After expiration of the timeout, without a window with a proper title, if the exception is ‘True’ the test case breaks, otherwise (if it is ‘False’) the test case continues its execution. Default values: timeout=60, exception=true.

  Example:

  +-----------------+-----------------------------------+----------------+---------------------+
  | ``Wait Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=10`` | ``exception=false`` |
  +-----------------+-----------------------------------+----------------+---------------------+


.. _system_keywords-window_keywords-maximize_window:

Maximize Window
---------------

  +---------------------+--------------------------+-------------------------+------------------------+
  | ``Maximize Window`` | ``<window_title_regex>`` | ``timeout = <seconds>`` | ``exception = <bool>`` |
  +---------------------+--------------------------+-------------------------+------------------------+

    Maximize the size of a window with a title name that fits with the regular expression. It is a best practice to maximize the window on which the following test case steps will work: that is to limit at maximum the ‘graphical noise’ coming from the rest of the GUI, optimizing the detection of the Alyvix keywords on the interested application window. After the imposed timeout expiration, without a living window with a proper title, if the exception is ‘True’ the test case breaks, otherwise (if it is ‘False’) the test case continues its execution. Default values: timeout=60, exception=true.

  Example:

  +---------------------+-----------------------------------+---------------+--------------------+
  | ``Maximize Window`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=5`` | ``exception=true`` |
  +---------------------+-----------------------------------+---------------+--------------------+


.. _system_keywords-window_keywords-show_window:

Show Window
-----------

  +-----------------+--------------------------+
  | ``Show Window`` | ``<window_title_regex>`` |
  +-----------------+--------------------------+

    Brings in foreground, without resizing, a window with a title name that fits the regular expression. This keyword has an immediate timeout and no exception.

  Example:

  +-----------------+-----------------------------------+
  | ``Show Window`` | ``synthetic.*monitoring.*alyvix`` |
  +-----------------+-----------------------------------+


.. _system_keywords-window_keywords-check_window:

Check Window
------------

  +------------------+--------------------------+
  | ``Check Window`` | ``<window_title_regex>`` |
  +------------------+--------------------------+

    Checks the existence of a window (in background or in foreground) with a title name that fits with the regular expression, returning a bool for further decision or logging steps. This keyword has an immediate timeout and no exception.

  Example:

  +----------+------------------+-----------------------------------+
  | ``${x}`` | ``Check Window`` | ``synthetic.*monitoring.*alyvix`` |
  +----------+------------------+-----------------------------------+
  | ``Log``  | ``${x}``         |                                   |
  +----------+------------------+-----------------------------------+


.. _system_keywords-window_keywords-close_window:

Close Window
------------

  +------------------+--------------------------+
  | ``Close Window`` | ``<window_title_regex>`` |
  +------------------+--------------------------+

    Closes a window, in background or in foreground, with a title name that fits with the regular expression. This keyword has an immediate timeout and no exception.

  Example:

  +------------------+-----------------------------------+
  | ``Close Window`` | ``synthetic.*monitoring.*alyvix`` |
  +------------------+-----------------------------------+


.. _system_keywords-window_keywords-wait_window_close:

Wait Window Close
-----------------

  +-----------------------+--------------------------+-------------------------+------------------------+
  | ``Wait Window Close`` | ``<window_title_regex>`` | ``timeout = <seconds>`` | ``exception = <bool>`` |
  +-----------------------+--------------------------+-------------------------+------------------------+

    Waits the timeout amount of seconds until a window, with a title name that fits with the regular expression, will be closed. After expiration of the timeout, without a window with a proper title, if the exception is ‘True’ the test case breaks, otherwise (if it is ‘False’) the test case continues its execution. Default values: timeout=60, exception=true.

  Example:

  +-----------------------+-----------------------------------+----------------+--------------------+
  | ``Wait Window Close`` | ``synthetic.*monitoring.*alyvix`` | ``timeout=30`` | ``exception=true`` |
  +-----------------------+-----------------------------------+----------------+--------------------+


.. _system_keywords-io_keywords:

I/O keywords
============


.. _system_keywords-io_keywords-send_keys:

Send Keys
---------

  +---------------+------------+------------------------+
  | ``Send Keys`` | ``<keys>`` | ``encrypted = <bool>`` |
  +---------------+------------+------------------------+

    Types a sequence of simulated keystrokes to the active window where the cursor is: regular characters (letters and numbers) can be stated as they are, while the following list of special ones have to be enclosed in braces. The encrypted option can be activated (encrypted=True) in case the string of keystrokes has been encrypted using alyvix_crypto_utility.bat through command prompt.

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

  +---------------+----------------------------+---------------------+
  | ``Send Keys`` | ``{Alt Down}{F4}{Alt Up}`` | ``encrypted=false`` |
  +---------------+----------------------------+---------------------+


.. _system_keywords-io_keywords-mouse_scroll:

Mouse Scroll
------------

  +------------------+-----------------------+----------------------------+
  | ``Mouse Scroll`` | ``steps = <scrolls>`` | ``direction = {down, up}`` |
  +------------------+-----------------------+----------------------------+

    Scrolls of a given steps, down or up, the active window where the focus is. Default values: steps=2, direction=up.

  Example:

  +------------------+-------------+--------------------+
  | ``Mouse Scroll`` | ``steps=3`` | ``direction=down`` |
  +------------------+-------------+--------------------+


.. _system_keywords-io_keywords-move_mouse:

Mouse Move
----------

  +----------------+-------------------------------------+-----------------------------------+
  | ``Mouse Move`` | ``<horizontal_pixel_coordinate_x>`` | ``<vertical_pixel_coordinate_y>`` |
  +----------------+-------------------------------------+-----------------------------------+

    Moves mouse pointer to given horizontal and vertical pixel coordinates within your screen. Keep in mind the positive verse of horizontal screen coordinate x is from left to right, that one of vertical coordinate y is from top to bottom: the origin of screen axes is at the point (x, y) = (0, 0) in the top-left corner. Sometimes leaving the mouse pointer in a certain position after a transaction can cause unintended interactions following.

  Example:

  +----------------+-------+-------+
  | ``Mouse Move`` | ``0`` | ``0`` |
  +----------------+-------+-------+


.. _system_keywords-performance_keywords:

Performance keywords
====================


.. _system_keywords-performance_keywords-add_perfdata:

Add Perfdata
------------

  +------------------+------------------------+-----------------------+-----------------------------------+------------------------------------+----------------------------------------------------------+
  | ``Add Perfdata`` | ``<performance_name>`` | ``value = <seconds>`` | ``warning_threshold = <seconds>`` | ``critical_threshold = <seconds>`` | ``state = {ok: 0, warning: 1, critical: 2, unknown: 3}`` |
  +------------------+------------------------+-----------------------+-----------------------------------+------------------------------------+----------------------------------------------------------+

    Declares a variable name, which should be an Alyvix keyword name: when that keyword will be executed, it will fill the variable with the measured performance and the rest of defined data (thresholds and states). It is convenient to add performance variables at the beginning of test cases: in this case we will know at what point the test eventually breaks. Default values: value=null, warning_threshold=None, critical_threshold=None, state=3. If a variable will not be filled (maybe because the test breaks before or at that point) the keyword state will return as ‘unknown’.

  Example:

  +------------------+------------------+-------------+-------------------------+--------------------------+-------------+
  | ``Add Perfdata`` | ``citrix_login`` |             |                         |                          |             |
  +------------------+------------------+-------------+-------------------------+--------------------------+-------------+
  | ``Add Perfdata`` | ``dummy_perf``   | ``value=1`` | ``warning_threshold=3`` | ``critical_threshold=5`` | ``state=0`` |
  +------------------+------------------+-------------+-------------------------+--------------------------+-------------+


.. _system_keywords-performance_keywords-print_perfdata:

Print Perfdata
--------------

  +--------------------+----------------------+-------------------------+
  | ``Print Perfdata`` | ``message=<string>`` | ``print_output=<bool>`` |
  +--------------------+----------------------+-------------------------+

    Prints all the performance variables added to a test case. Default values: a message will be printed describing the overall status at the end of the test case execution, eventually with the name of the last performance variable that has been measured and filled before a failure, print_output=true.

  Example:

  +--------------------+
  | ``Print Perfdata`` |
  +--------------------+


.. _system_keywords-performance_keywords-store_perfdata:

Store Perfdata
--------------

  +--------------------+---------------------------------------------+
  | ``Store Perfdata`` | ``<path_to_testcase_database_file.sqlite>`` |
  +--------------------+---------------------------------------------+

    Saves in several tables of the specified SQLite database file all the data about the execution of a test case. New data are added to past data that comes to previous execution of the test case: in this way, Alyvix probes can track test case outputs during the time. The data tables are 3: runs contains a row for each execution of the test case and in each row there are an execution timestamp and transaction performances (in milliseconds) related to used keywords. sorting contains a new row just when something is changed in the test case execution (e.g. it fails, it runs different keywords) and in each row there are execution timestamp and the execution sequence of keywords: integer numbers (starting from 0) to sort successful executed keywords, -1 to label failed keywords and NULL to label unused keywords. thresholds contains a new row just when used keywords or keyword thresholds change and in each row there are execution timestamps, warning and critical thresholds of used keywords.

  Example:

  +--------------------+----------------------------------------------+
  | ``Store Perfdata`` | ``C:\\alyvix_testcases\\citrix_word.sqlite`` |
  +--------------------+----------------------------------------------+


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

    Grabs a screenshot and saves it into the output folder, which can be specified as an argument (–outputdir <path_to_folder>) of the alyvix_pybot.bat through command prompt. By default the extension of the file is .png, but it is possible to specify a .jpg as the extension after the filename.

  Example:

  +-----------------------+---------------+
  | ``Alyvix Screenshot`` | ``login.jpg`` |
  +-----------------------+---------------+
