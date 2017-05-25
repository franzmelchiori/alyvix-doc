****************
Check deployment
****************

Follow these steps to be sure everything is well deployed and works fine, both in case of install with or without Internet.

  1. run Command Prompt, execute the following command and check the presence of pyqt 4.10.4 py27_1, pillow 2.7.0 py27_0 and alyvix 2.4.1 py27_1 within the list of installed conda packages:

    conda list “alyvix|pillow|pyqt”

    01_alyvix_install_check

  2. run Services (under Control Panel\System and Security\Administrative Tools in File Explorer) and and check the presence of Alyvix Wpm Service

    02_alyvix_install_check

  3. browse Anaconda folder to <path_to_anaconda>\Lib\site-packages\alyvix\robotproxy, where Alyvix will save your test case .py libraries of keywords, and create (within \robotproxy) the folder \alyvix_testcases, where you will save your test case .robot scripts

  4. run RIDE, the Alyvix test case editor, double clicking <path_to_anaconda>\Scripts\RIDE.lnk; could be useful to send its shortcut to desktop or taskbar

  5. create a new project, clicking on file menu: type its name (e.g my_first_alyvix_testcase_suite) and point to the folder <path_to_anaconda>\Lib\site-packages\alyvix\robotproxy\alyvix_testcases you have created

  6. create a new test case, right clicking on the project name (e.g my_first_alyvix_testcase_suite) in the left panel of the editor: type its name (e.g my_first_alyvix_testcase)

  7. import the Alyvix library of basic keywords: click on the project name, then on library button, type alyvixlib and click OK button; a library import is successful if its name appears black, otherwise is red

    07_alyvix_ride_test_case_suite

  8. edit the test case, clicking on its name and type the following command (and its arguments) in the first table row, from the first to the third column:

    Create Process | C:\\Program Files\\Internet Explorer\\iexplore.exe | http://www.alyvix.com/

    08_alyvix_ride_test_case_edit

  9. save the test case with CTRL+S and run it with F8: if Internet Explorer opens Alyvix website, you are ready to build serious Alyvix test cases
