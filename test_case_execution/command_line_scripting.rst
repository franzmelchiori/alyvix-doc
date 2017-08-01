.. _commandline_scripting:

**********************
Command line scripting
**********************


alyvix_pybot manual page
========================


Synopsis
--------

    ``alyvix_pybot <testcase_path> [options]``


Description
-----------

    ``alyvix_pybot`` is an **Alyvix CLI tool**, stored in ``C:\Anaconda2\Scripts\``, that is able to **run a test case** out of :ref:`RIDE <testcase_editor>` **for scripting purposes**.

    It needs a valid **Alyvix test case** ``.robot`` file (build with :ref:`RIDE <testcase_editor>`) providing its ``<testcase_path>`` (e.g. ``C:\Anaconda2\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\test.robot``)

    It returns ..


Options
-------

    ``--outputdir <report_path>`` log_folder

    ``--exitcode <error_level>`` the_exitcode


Example
-------

    The following example ``run_test.bat`` can run the Alyvix test case ``test.robot`` and print out its HTML report:

        .. code-block:: bat

                call alyvix_pybot "C:\Anaconda2\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\test.robot" --outputdir "C:\alyvix_reports\test\"
                pause
