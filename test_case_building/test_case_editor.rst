.. _testcase_editor:

****************
Test case editor
****************


.. _testcase_editor-basic_operations:

Basic operations
================

**RIDE** is the Alyvix editor for its test cases, where to write new tests, to edit existing ones, etc. It is also the place from where one can run the Alyvix tools to define new Alyvix visual keywords (e.g. *Image Finder*).

First of all, you have to run the *RIDE shortcut* within the *Anaconda path* to start working with it:

  ``C:\Anaconda2\Scripts\RIDE.lnk``

You can notice common menu and tool bars. The very first operation to start building a new test case is to create a *New Project* (*File* > *New Project*):

  .. image:: pictures/ride_01b_project_window.png

Insert a valid project name (recommendation: lowercased, with underscores instead of spaces, e.g. ``guide_project``) and browse the folder ``\alyvix_testcases`` that you should have created under the Alyvix ``\robotproxy`` folder:

  ``C:\Anaconda2\Lib\site-packages\alyvix\robotproxy\alyvix_testcases``

The file type to select should be *File* and file format should be *Robot*. The editor will save, for the project you work on, the test case scripts that you build (keyword tables) and the Python libraries that you import (system and visual keyword modules) in a ``.robot`` text file.

Now, in the *RIDE main window* on the left there is a *tree view pane*: it lists the current open project (projects are also called "Test Suite") with its test cases. Clicking on the project name, a pane with the project settings appears (as an edit tab) on the right, from where it is possible to import libraries or to add lists (arrays):

  .. image:: pictures/ride_01a_project_window.png

Clicking on the *Library button* you can import external libraries of keywords that you can use to build the test case. It is necessary to import the Alyvix library of system keywords: type ``alyvixlib`` and press *OK*. Define at least one visual keyword for a test case and then RIDE saves its Alyvix library of visual keywords. That library is a Python module, it has a filename like *AlyvixProxy<project_name>* and it is a .py file (e.g. ``AlyvixProxyguide_project.py``) within the ''\robotproxy'' folder:

  .. image:: pictures/ride_01c_import_library.png

Type a library name (``alyvixlib`` at the beginning of a test case building, then ``AlyvixProxy<project_name>`` when you will define at least one visual keyword) and click on *OK* to import it: the library name will be listed in black (or in red, if RIDE has not been able to find it).


.. _testcase_editor-editor_buttons:

Editor buttons
--------------

The most useful *editor buttons* are the following ones:

  +-------------------------------------------------+
  | .. image:: pictures/ride_01e_toolbar_alyvix.png |
  +-------------------------------------------------+

    *Alyvix button* opens the **Alyvix** keyword selector, where the *visual keywords* (you have created for the current project) are listed. Visual keywords can be edited and new ones can be added (clicking on the *New* button to open the *Alyvix Finder selector*).

  +-----------------------------------------------+
  | .. image:: pictures/ride_01d_toolbar_save.png |
  +-----------------------------------------------+

    **Save** buttons allows users to save *current* ``.robot`` file, they are working on, or *all* ``.robot`` project files. Remember to click on the disk-with-star icon to apply all changes you have done on a test case for running the up-to-date version of the test case.

  +------------------------------------------------+
  | .. image:: pictures/ride_01f_toolbar_start.png |
  +------------------------------------------------+

    **Run** and **stop** buttons can execute (click on play button) or terminate (double click on stop button) the current project running (its current test cases).


.. _testcase_editor-editor_shortcuts:

Editor shortcuts
----------------

The most useful *editor and Alyvix shortcuts* are the following ones:

  +--------------------------------------------------------------------+---------------------+
  | Accept and exit **Alyvix** visual selection mode                   | :kbd:`CTRL+O`       |
  +--------------------------------------------------------------------+---------------------+
  | Unlimited extend **ROI boundaries** towards one or more directions | :kbd:`ARROWS`       |
  +--------------------------------------------------------------------+---------------------+
  | Undo **Alyvix** visual selections                                  | :kbd:`CTRL+Z`       |
  +--------------------------------------------------------------------+---------------------+
  | **Copy** selected **keyword name** in Alyvix selector              | :kbd:`CTRL+C`       |
  +--------------------------------------------------------------------+---------------------+
  | **Copy** selected **cell/row(s)**                                  | :kbd:`CTRL+C`       |
  +--------------------------------------------------------------------+---------------------+
  | **Cut** selected cell/row(s)                                       | :kbd:`CTRL+X`       |
  +--------------------------------------------------------------------+---------------------+
  | **Paste** copied **keyword name** in Alyvix selector               | :kbd:`CTRL+V`       |
  +--------------------------------------------------------------------+---------------------+
  | **Paste** selected **cell/row(s)**                                 | :kbd:`CTRL+V`       |
  +--------------------------------------------------------------------+---------------------+
  | **Undo** last operation                                            | :kbd:`CTRL+Z`       |
  +--------------------------------------------------------------------+---------------------+
  | **Insert** a blank **row** above the selected row                  | :kbd:`CTRL+I`       |
  +--------------------------------------------------------------------+---------------------+
  | **Insert** a blank **cell** left to the selected cell              | :kbd:`CTRL+SHIFT+I` |
  +--------------------------------------------------------------------+---------------------+
  | **Delete** selected **keyword** in Alyvix selector                 | :kbd:`CTRL+D`       |
  +--------------------------------------------------------------------+---------------------+
  | **Delete** the selected **row(s)**                                 | :kbd:`CTRL+D`       |
  +--------------------------------------------------------------------+---------------------+
  | **Delete** the selected **row(s)**                                 | :kbd:`CTRL+SHIFT+D` |
  +--------------------------------------------------------------------+---------------------+
  | **Move up** the selected row(s)                                    | :kbd:`ALT+↑`        |
  +--------------------------------------------------------------------+---------------------+
  | **Move down** the selected row(s)                                  | :kbd:`ALT+↓`        |
  +--------------------------------------------------------------------+---------------------+
  | **Comment** the selected row(s)                                    | :kbd:`CTRL+3`       |
  +--------------------------------------------------------------------+---------------------+
  | **Uncomment** the selected row(s)                                  | :kbd:`CTRL+4`       |
  +--------------------------------------------------------------------+---------------------+
  | **Autocomplete** keyword from imported libraries                   | :kbd:`CTRL+SPACE`   |
  +--------------------------------------------------------------------+---------------------+
  | **Save** current file                                              | :kbd:`CTRL+S`       |
  +--------------------------------------------------------------------+---------------------+
  | **Save all** project files                                         | :kbd:`CTRL+SHIFT+S` |
  +--------------------------------------------------------------------+---------------------+
  | **Run** test cases of the current project                          | :kbd:`F8`           |
  +--------------------------------------------------------------------+---------------------+
  | **Stop** test cases of the current running project                 | :kbd:`CTRL+F8`      |
  +--------------------------------------------------------------------+---------------------+
  | Open the last produced **report**                                  | :kbd:`CTRL+L`       |
  +--------------------------------------------------------------------+---------------------+


.. _testcase_editing:

Test case editing
=================

Right click on the project name (e.g. ``guide_project``) in the left pane of the RIDE main window and click on *New test case* option. Insert a name for the test case you are creating (recommendation: lowercased, with underscores instead of spaces, e.g. ``guide_project``, the same as the project name).

  .. image:: pictures/ride_02a_test_window.png

Now, clicking on the test case name you visualize its main table on the right (as an edit tab).

  .. image:: pictures/ride_02b_test_window.png

This is the space where to edit the test case, typing keywords in different kind of syntaxes. For the Alyvix basic keywords, the main syntax is the following one: a keyword in a cell of the first column and the keyword arguments (one or more) in the subsequent cells.

For example, in the following test case script there is one single Alyvix basic keyword which is ``Create Process`` from ``alyvixlib``: it takes two arguments, the first one is the process you want to run (e.g. Internet Explorer) and the second one is the Internet address you want to browse (e.g. the Alyvix website).

  .. image:: pictures/ride_03a_test_case.png

In the :ref:`system_keywords` section about ``alyvixlib`` you can find the complete list of the Alyvix basic keywords and their how-to-use description (e.g. syntax, mandatory or optional arguments and their values, effects).

Alyvix visual keywords, that you will be able to define using the Alyvix tools (e.g. Image Finder, Rect Finder, Text Finder, Object Finder), simply take at minimum no arguments or at maximum a number of arguments with text strings (to find or to type) or keyboard shortcuts (to send).

For example, you could define a keyword to detect that a browser has rendered the homepage of the Alyvix website. The keyword could work just detecting images, so it does not take text arguments and you could name it ``alyvix_website_ready``. In this case, you could use the keyword within a test case just typing its name. RIDE can equally interpret ``Alyvix Website Ready``.

  .. image:: pictures/ride_03b_test_case.png

In the :ref:`visual_keywords` section you can learn how to build Alyvix visual keywords.

There are also several Robot Framework keywords and their syntaxes. Take a look at the complete list of Robot Framework standard libraries and their keywords browsing the following website:

  http://robotframework.org/robotframework/#user-guide

For example, in the following test case the variable ``${time}`` is defined with the current hour and the variable ``${work}`` is ``True`` or ``False`` depending on the value of ``${time}`` (if it is in the range of working hours or not). The final value of ``${work}`` is printed out.

  .. image:: pictures/ride_03c_test_case.png

RIDE also allows you to create *subtables* to use in projects: it is like execute secondary test cases in main ones. Subtables have a name and you can type that name in a test case of the same project to execute the keywords listed in that subtable. Right click on the project name (in tree view on the left pane) and select *New user keyword* to create subtables.

  .. image:: pictures/ride_04a_sub_tables.png

A best practice is to create a ``setup`` and a ``teardown`` subtables. Then you can set to execute them at the beginning of a test case and at its termination (both in case of success or failure).

It is a good practice because at startup, you can declare the desired performances and at termination, you can print the collected performances in any case. If something has gone wrong, in any point of the test case, Alyvix can output which the last filled performance has been and why the subsequent has failed.

  .. image:: pictures/ride_04b_sub_tables.png

Moreover, the exit subtable is the right place where list keywords to close (or even to kill) any possible windows on screen that the test case can have open. This is good for restoring the original and clean state of the screen, from where to rerun the test.

  .. image:: pictures/ride_04c_sub_tables.png

To set subtables as test case procedures during *setup* or *teardown*, click on a test case name in the tree view on the left pane of RIDE, click on *Settings >>* button above the right pane, click the *Edit* button left to the *Setup* or *Teardown* edit boxes and finally type the subtable name (e.g. ``setup``, ``teardown``).

  .. image:: pictures/ride_04d_sub_tables.png

  .. image:: pictures/ride_02c_test_settings_window.png

RIDE also allows using subtables as keywords in test cases. In this way, you can pack together Robot Framework and Alyvix commands that represent a frequent routine, under a subtable that can be used in test cases as a single regular keyword. The latter can even take arguments to use within its related subtable.

  .. image:: pictures/ride_04e_sub_tables.png
