.. _commandline_scripting:

**********************
Command line scripting
**********************


    .. code-block:: bat

        @echo on
        c:
        call C:\Anaconda2\Scripts\alyvix_pybot.bat "C:\<path_to>\<alyvix_testcases>\<testcase_name>.robot" --outputdir "C:\<path_to>\<alyvix_reports>\<testcase_name>\"
        pause

Example:

    .. code-block:: bat

        @echo on
        c:
        call C:\Anaconda2\Scripts\alyvix_pybot.bat "C:\Anaconda2\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\test.robot" --outputdir "C:\alyvix_reports\test\"
        pause
