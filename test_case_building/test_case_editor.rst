.. _testcase_editor:

****************
Test case editor
****************


.. _testcase_editor-basic_operations:

Basic operations
================

**RIDE** is the editor to build Alyvix test cases: it is the place where to compose new tests or to edit existing ones. From the *RIDE* you can also run the :ref:`Alyvix tools <testcase_editor-editor_buttons_shortcuts>` to define new :ref:`Alyvix visual keywords <visual_keywords>` (e.g. *Image Finder*).

Firstly, run the **RIDE shortcut** (you can find it in the *Python path*) to start working with the editor:

  ``C:\Python27\Scripts\ride.lnk``

You can notice common menu and tool bars. Create a **New Project** (*File* > *New Project*) to start building a new test case:

  .. image:: pictures/ride_01b_project_window.png

Insert a valid **project name** (recommendation: type a lowercased name, with underscores instead of spaces, e.g. ``guide_project``) and browse the folder ``\alyvix_testcases`` that you should create under the Alyvix ``\robotproxy`` folder as follows:

  ``C:\Python27\Lib\site-packages\alyvix\robotproxy\alyvix_testcases``

Select **File** and **Robot** as the file type and format of the test case. The editor will save the test case script in a ``.robot`` text file, that is a system of keyword tables and Python modules (system and visual keywords) you will use.

.. note::
    Have a look at the :ref:`Alyvix file structure <backup>` to know the proper way to **backup** and **migrate** test cases.

In the *RIDE main window* on the left there is a *tree view pane*: it lists the current **open project** (called *Test Suite*) with its test cases. Clicking on the project name, a pane with the **project settings** appears on the right as an *edit tab*, from where it is possible to import libraries or to add lists (arrays):

  .. image:: pictures/ride_01a_project_window.png

Click on the **Library** button to import libraries of keywords that you can use to make the test case script. It is necessary to import the **basic Alyvix library** of its system keywords: type ``alyvixlib`` and press *OK*. Define at least one :ref:`visual keyword <visual_keywords>` for a test case and then RIDE saves its **Alyvix library of visual keywords**. That library is a Python module, it has a filename like *AlyvixProxy<project_name>* and it is a .py file (e.g. ``AlyvixProxyguide_project.py``) saved in the ``\robotproxy`` folder:

  .. image:: pictures/ride_01c_import_library.png

.. warning::
  Basically, import ``alyvixlib`` when you start to build a test case; import ``AlyvixProxy<project_name>`` when you define at least one visual keyword. Moreover, you can import ``AlyvixProxy<another_project_name>`` to **reuse visual keywords defined in another test case** saving time in rebuilding and maintenance. A library name is listed in red (and not in black) if the editor has not been able to find or load it.


.. _testcase_editor-editor_buttons_shortcuts:
.. _testcase_editor-editor_buttons:
.. _testcase_editor-editor_shortcuts:

Editor buttons and shortcuts
============================

The most useful **editor buttons**:

  .. image:: pictures/ride_01e_toolbar_alyvix.png

..

     *Alyvix button* opens the **Alyvix selector**, where the :ref:`visual keyword <visual_keywords>` for the current project are listed. Visual keywords can be edited and new ones can be added: click on the **New** button to open the *Alyvix selector*.

  .. image:: pictures/ride_01d_toolbar_save.png

..

     **Save** buttons allows to save the *current* ``.robot`` file or *all* ``.robot`` project files. Remember to click on the disk-with-star icon to apply all changes you have done on a test case for running the up-to-date version of the test case.

  .. image:: pictures/ride_01f_toolbar_start.png

..

     **Run** and **stop** buttons can respectively execute (play button) or terminate (stop button) the current project.

  ..


The **Alyvix shortcuts**:

  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+O`              | visual definition    | Accept and **exit the Alyvix visual selection mode**               |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`SPACE + RIGHT CLICK` | visual definition    | **Highlight and autocontour visual component candidates**          |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`RIGHT CLICK`         | visual components    | **Autocontour visual component candidates**                        |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`RIGHT CLICK`         | component ROI edges  | **Push component ROI edges to infinity**                           |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL + LEFT CLICK`   | component SELections | **Reset component ROI edges** near around selections inside        |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL + RIGHT CLICK`  | selected components  | **Remove components** both SELections and ROIs                     |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`ARROWS`              | ROI selection        | **Extend unlimitedly ROI boundaries** in the visual selection mode |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+Z`              | visual definition    | **Undo visual selections** in the visual selection mode            |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+Y`              | visual definition    | **Redo visual selections** in the visual selection mode            |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+C`              | keyword selector     | **Copy** selected **keyword name** in Alyvix selector              |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+V`              | keyword selector     | **Paste** copied **keyword name** from Alyvix selector             |
  +----------------------------+----------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+D`              | keyword selector     | **Delete** selected **keyword** in Alyvix selector                 |
  +----------------------------+----------------------+--------------------------------------------------------------------+


The most useful **editor shortcuts**:

  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+C`       | **Copy** the selected **cell/row(s)**                              |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+X`       | **Cut** the selected **cell/row(s)**                               |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+V`       | **Paste** the selected **cell/row(s)**                             |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+Z`       | **Undo** the last editor operation                                 |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+I`       | **Insert a blank row** above the selected row                      |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+SHIFT+I` | **Insert a blank cell** left to the selected cell                  |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+D`       | **Delete** the selected **row(s)**                                 |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+SHIFT+D` | **Delete** the selected **row(s)**                                 |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`ALT+UP`       | **Move up** the selected **row(s)**                                |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`ALT+DOWN`     | **Move down** the selected **row(s)**                              |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+3`       | **Comment** the selected **row(s)**                                |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+4`       | **Uncomment** the selected **row(s)**                              |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+SPACE`   | **Autocomplete keyword** from imported libraries                   |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+S`       | **Save current file**                                              |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+SHIFT+S` | **Save all project files**                                         |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`F8`           | **Run the test case** of the current project                       |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+F8`      | **Stop the test case** of the current running project              |
  +---------------------+--------------------------------------------------------------------+
  | :kbd:`CTRL+L`       | **Open the last produced report**                                  |
  +---------------------+--------------------------------------------------------------------+


.. _testcase_editing:

Test case editing
=================

Right click on the :ref:`project name <testcase_editor-basic_operations>` (e.g. ``guide_project``) in the left pane of the **RIDE main window** and click on **New test case** option. Insert a name for the test case you are creating (recommendation: type a lowercased, with underscores instead of spaces, e.g. ``guide_project``, the same as the project name).

  .. image:: pictures/ride_02a_test_window.png

Click on the test case name you visualize its **main table** on the right (as an edit tab).

  .. image:: pictures/ride_02b_test_window.png

This is the space where to edit the test case, typing keywords in different kind of syntaxes. The **main syntax for Alyvix keywords** is as follows: a keyword in a cell of the first column and the keyword arguments (one or more) in the subsequent cells.

For example, in the following test case script there is one single Alyvix basic keyword which is :ref:`Create Process <system_keywords-debug_keywords-create_process>` from ``alyvixlib``: it takes two arguments, the first one is the process you want to run (e.g. Internet Explorer) and the second one is the Internet address you want to browse (e.g. the Alyvix website).

  .. image:: pictures/ride_03a_test_case.png

In the :ref:`system keywords <system_keywords>` section about ``alyvixlib`` you can find the complete list of the **Alyvix basic keywords** and their how-to-use description (e.g. syntax, mandatory or optional arguments and their values, effects).

:ref:`Alyvix visual keywords <visual_keywords>`, that you can define using the :ref:`Alyvix tools <testcase_editor-editor_buttons_shortcuts>` (e.g. Image Finder, Rect Finder, Text Finder, Object Finder), simply take at minimum no arguments or at maximum :ref:`a number of arguments <visual_keywords-name_components>` with text strings (to find or to type) or keyboard shortcuts (to send).

For example, you could define a keyword to detect if a browser has rendered the homepage of the Alyvix website. The keyword could work just :ref:`detecting images <visual_keywords-image_finder>`, so it does not take text arguments and you could name it ``alyvix_website_ready``. In this case, you could use the keyword within a test case just typing its name. RIDE can equally interpret ``Alyvix Website Ready``.

  .. image:: pictures/ride_03b_test_case.png

In the :ref:`visual keywords <visual_keywords>` section you can learn how to build **Alyvix visual keywords**. There are also several **Robot Framework keywords** and their syntaxes. Take a look at the complete list of `Robot Framework standard libraries <http://robotframework.org/robotframework/#user-guide>`_.

For example, in the following test case the variable ``${time}`` is defined with the current hour and the variable ``${work}`` is ``True`` or ``False`` depending on the value of ``${time}`` (if it is in the range of working hours or not). The final value of ``${work}`` is printed out.

  .. image:: pictures/ride_03c_test_case.png

RIDE allows you to create **subtables** to use in projects: it is like execute secondary test cases in main ones. Subtables have a name and you can type that name in a test case of the same project to execute the keywords listed in that subtable. Right click on the project name (in tree view on the left pane) and select **New user keyword** to create subtables.

  .. image:: pictures/ride_04a_sub_tables.png

A :ref:`best practice <testcase_sections>` is to create a ``setup`` and a ``teardown`` subtables. Then you can set to execute them at the beginning and at the termination of a test case both in case of success or failure. At startup you want declare the desired performances and at termination you want print the collected performances in any case: if something has gone wrong, in any point of the test case, Alyvix can output the last performance that has successfully exited and why the subsequent one has failed.

  .. image:: pictures/ride_04b_sub_tables.png

Moreover, the **exit section** is the right place where list keywords to close (or even to kill) any possible windows on screen that the test case can have open. This is good for **restoring the original and clean state** of the screen, from where to rerun the test.

  .. image:: pictures/ride_04c_sub_tables.png

To set subtables as test case procedures during *setup* or *teardown*, click on a test case name in the tree view on the left pane of RIDE, click on **Settings** button above the right pane, click the **Edit** button left to the *Setup* or *Teardown* edit boxes and finally type the subtable name (e.g. ``setup``, ``teardown``).

  .. image:: pictures/ride_04d_sub_tables.png

..

  .. image:: pictures/ride_02c_test_settings_window.png

RIDE allows **using subtables as keywords** in test cases. In this way, you can pack together Robot Framework and Alyvix commands that represent a frequent routine. Subtables can be used in test cases as single regular keywords, even taking arguments.

  .. image:: pictures/ride_04e_sub_tables.png
