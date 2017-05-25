****************
Check deployment
****************

Follow these steps to be sure everything is well deployed and works fine, both in case of install with or without Internet.

  1. run Command Prompt, execute the following command and check the presence of ``pyqt 4.10.4 py27_1``, ``pillow 2.7.0 py27_0`` and ``alyvix 2.4.1 py27_1`` within the list of installed conda packages:

    ``conda list “alyvix|pillow|pyqt”``

    .. image:: pictures/01_alyvix_install_check.png

  2. run Services (under Control Panel > System and Security > Administrative Tools) and and check the presence of Alyvix Wpm Service

    .. image:: pictures/02_alyvix_install_check.png

  3. browse Anaconda folder ``C:\Anaconda2\Lib\site-packages\alyvix\robotproxy`` (where Alyvix will save your test case .py libraries of keywords) and create the folder ``\alyvix_testcases``, where you will save your test case .robot scripts

  4. run RIDE, the Alyvix test case editor, double clicking ``C:\Anaconda2\Scripts\RIDE.lnk``; could be useful to send its shortcut to desktop or taskbar

  5. create a "New Project", clicking on the "File" menu of RIDE: type its name (e.g my_first_alyvix_testcase_suite) and point to the folder ``C:\Anaconda2\Lib\site-packages\alyvix\robotproxy\alyvix_testcases``

  6. create a "New Test Case", right clicking on the project name (e.g my_first_alyvix_testcase_suite) in the left panel of the editor: type its name (e.g my_first_alyvix_testcase)

  7. import the Alyvix library of basic keywords: click on the project name, then on the "Library" button, type ``alyvixlib`` and click the "OK" button; a library import will be successful if its name appears black, otherwise it will be red

    .. image:: pictures/07_alyvix_ride_test_case_suite.png

  8. edit the test case, clicking on its name and type the following command (and its arguments) in the first table row, from the first to the third column:

    +--------------------+--------------------------------------------------------+----------------------------+
    | ``Create Process`` | ``C:\\Program Files\\Internet Explorer\\iexplore.exe`` | ``http://www.alyvix.com/`` |
    +--------------------+--------------------------------------------------------+----------------------------+

    .. image:: pictures/08_alyvix_ride_test_case_edit.png

  9. save the test case with :kbd:`CTRL+S` and run it with :kbd:`F8`: if Internet Explorer opens Alyvix website, you are ready to build serious Alyvix test cases
