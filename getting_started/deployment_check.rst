****************
Deployment check
****************

Follow these steps to be sure that everything is well deployed and works fine:

  1. run **Command Prompt**, execute the following command and check the presence of *alyvix 2.5.1 py27_1* as installed conda package: ``conda list alyvix``

  2. browse Anaconda folder ``C:\Anaconda2\Lib\site-packages\alyvix\robotproxy`` (where Alyvix will save your test case .py libraries of keywords) and create the folder ``\alyvix_testcases``, where you will save your test case .robot scripts

  3. run **RIDE**, the Alyvix test case editor, running ``C:\Anaconda2\Scripts\RIDE.lnk``: it could be useful to send its shortcut to the desktop or the taskbar

  4. create a *New Project*, clicking on the *File* menu of **RIDE**: type its name (e.g ``my_first_alyvix_testcase_suite``) and point to the folder ``C:\Anaconda2\Lib\site-packages\alyvix\robotproxy\alyvix_testcases``

  5. create a *New Test Case*, right clicking on the project name (e.g *My First Alyvix Testcase Suite*) in the left panel of the editor: type its name (e.g ``my_first_alyvix_testcase``)

  6. import the Alyvix library of basic keywords: click on the project name, then on the *Library* button, type ``alyvixlib`` and click the *OK* button: a library import is successful if its name appears black, otherwise it will be red:

    .. image:: pictures/07_alyvix_ride_test_case_suite.png

  7. edit the test case (clicking on its name) and type the following command (and its arguments) in the first table row, from the first to the third column:

    +--------------------+--------------------------------------------------------+----------------------------+
    | ``Create Process`` | ``C:\\Program Files\\Internet Explorer\\iexplore.exe`` | ``http://www.alyvix.com/`` |
    +--------------------+--------------------------------------------------------+----------------------------+

    .. image:: pictures/08_alyvix_ride_test_case_edit.png

  8. save the test case with :kbd:`CTRL+S` and run it with :kbd:`F8`: if Internet Explorer opens Alyvix website, you are ready to build serious Alyvix test cases!
