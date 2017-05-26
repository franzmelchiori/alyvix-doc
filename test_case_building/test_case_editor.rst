****************
Test case editor
****************


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

Clicking on the *Library button* you can import either the necessary Alyvix library of system keywords, typing ``alyvixlib``, visual ones and others. When you define at least one Alyvix keyword within a test case, RIDE saves a Python module as the Alyvix library of visual keywords for that test case. That is a .py file within the robotproxy folder and with a filename like AlyvixProxy<project_name> (e.g. ``AlyvixProxyguide_project``):

  .. image:: pictures/ride_01c_import_library.png

Type a library name (alyvixlib at the beginning of a test case building, then AlyvixProxy<project_name> when you define at least one Alyvix keyword) and click on OK to import it: the library name will be listed in black or in red, if RIDE has not been able to find it.

ride_01d_toolbar_save



Save buttons allows users to save current .robot file, they are working on, or all project .robot files. Remember to click on disk-with-star icon to apply all changes you have done on a test case in order to run the up-to-date version of that test case.

ride_01e_toolbar_alyvix



Alyvix button opens the Alyvix keyword selector, where the custom keywords (you have created for that project) are listed, can be edited and can be added (clicking on the ‘New’ button to open the Alyvix Finder selector).

ride_01f_toolbar_start



Run and stop buttons can execute (click on play button) or terminate (double click
on stop button) the current project (so its selected test cases).

The most useful RIDE shortcuts are the following ones:

Autocomplete keyword from imported libraries: CTRL + Space
Comment the selected row(s): CTRL + 3
Uncomment the selected row(s): CTRL + 4
Copy selected cell/row(s): CTRL + C
Cut selected cell/row(s): CTRL + X
Paste selected cell/row(s): CTRL + V
Undo last operation: CTRL + Z
Save current file: CTRL + S
Save all project files: CTRL + SHIFT + S
Insert a blank row above the selected row: CTRL + I
Insert a blank cell left to the selected cell: CTRL + SHIFT + I
Delete the selected row(s): CTRL + D
Delete the selected cell(s): CTRL + SHIFT + D
Move up the selected row(s): ALT + ↑
Move down the selected row(s): ALT + ↓
Run test cases of the current project: F8
Stop test cases of the current running project: CTRL + F8
Open the last produced report: CTRL + L


Test case editing
=================

Right click on the project name in the left pane of the RIDE main window and click on ‘New test case’ option. Insert a name for the test case you are creating (recommendation: lowercased, with underscores instead of spaces).

ride_02a_test_window

Now, clicking on the test case name you visualize its main table on the right (as an edit tab).

ride_02b_test_window

This is the space where to edit the test case, typing keywords in different kind of syntaxes. For the Alyvix basic keywords, the main syntax is the following one: a keyword in a cell of the first column and the keyword arguments (one or more) in the subsequent cells. For example, the following test case scripts one single Alyvix basic keyword that is ‘Create Process’ of alyvixlib: it takes two arguments, the first one is the process you want to run (e.g. Internet Explorer) and the second one is the Internet address you want to browse (e.g. the Alyvix website).

ride_03a_test_case

In the reference section about alyvixlib you can find the complete list of the Alyvix basic keywords and their how-to-use description (e.g. syntax, mandatory or optional arguments and their values, effects).

Alyvix custom keywords, that you will be able to define using the Alyvix tools (e.g. Image Finder, Rect Finder, Text Finder, Object Finder), simply take at minimum no arguments or at maximum a number of arguments with text strings (to find or to type) or keyboard shortcuts (to send). For example, you could define a keyword to detect that a browser has rendered the homepage of the Alyvix website. The keyword could work just detecting images, so it does not take text arguments and you could name it ‘alyvix_website_ready’. In this case, you could use the keyword within a test case just typing its name. RIDE can equally interpret ‘Alyvix Website Ready’.

ride_03b_test_case

There are also several Robot Framework keywords and their syntaxes. Take a look at the complete list of Robot Framework standard libraries and their keywords browsing the following website:

http://robotframework.org/robotframework/#user-guide

For example, in the following test case the variable ${time} is defined with the current hour and the variable ${work} is True or False depending on the value of ${time}, if it is in the range of working hours or not. The final value of ${work} is printed out.

ride_03c_test_case

RIDE also allows creating subtables to use in projects: it is like execute secondary test cases in main ones. Subtables have a name and you can type that name in a test case of the same project to execute the keywords listed in that subtable. Right click on the project name (in tree view on the left pane) and select ‘New user keyword’ to create subtables.

ride_04a_sub_tables

Best practice is to create a setup and an exit subtables. Then you can set to execute them at the beginning of a test case and at its termination both in case of success or failure.

It is a good practice because at startup, you can declare the desired performances and at termination, you can print the collected performances in any case. If something has gone wrong, in any point of the test case, Alyvix can output which the last filled performance is and why the subsequent has failed.

ride_04b_sub_tables

Moreover, the exit subtable is the right place where list keywords to close (or even to kill) any possible windows on screen that the test case can have open. This is good for restoring the original and clean state of the screen, from where to rerun the test.

ride_04c_sub_tables

To set subtables as test case procedures during setup or teardown, click on a test case name in the tree view on the left pane of RIDE, click on ‘Settings >>’ button above the right pane, click the ‘Edit’ button left to the ‘Setup’ or ‘Teardown’ edit boxes and finally type the subtable name (e.g. setup, exit).

ride_04d_sub_tables

ride_02c_test_settings_window

RIDE also allows using subtables as keywords in test cases. In this way, you can pack together Robot Framework and Alyvix commands that represent a frequent routine, under a subtable that can be used in test cases as a single regular keyword. The latter can even take arguments to use within its related subtable.

ride_04e_sub_tables
