.. _commandline_scripting:

**********************
Command line scripting
**********************


.. _commandline_scripting_alyvix_pybot_manual_page:

alyvix_pybot manual page
========================


Synopsis
--------

    ``alyvix_pybot <testcase_path> [options]``


Description
-----------

    ``alyvix_pybot`` is an **Alyvix CLI tool**, stored in ``C:\Python27\Scripts\``, that is able to **run a test case** out of :ref:`RIDE <testcase_editor>` **for scripting purposes**.

    It needs a valid **Alyvix test case** ``.robot`` file (build with :ref:`RIDE <testcase_editor>`) providing its ``<testcase_path>`` (e.g. ``C:\Python27\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\test.robot``)

    At the end of a test case execution, ``alyvix_pybot`` prints out the :ref:`performance message <commandline_output>` in the Command Prompt.


Options
-------

    ``--outputdir <report_path>`` sets the folder path where to save the test case report

    ``--exitcode <error_level>`` forces the overall ``errorlevel`` code of the test case if it will break

            * ``0`` **OK**
            * ``1`` **WARNING**
            * ``2`` **CRITICAL**
            * ``3`` **UNKNOWN**

        The default overall ``errorlevel`` code is ``2`` **CRITICAL**.


Example
-------

    The following example ``run_test.bat`` can run the Alyvix test case ``test.robot`` and print out its HTML report:

        .. code-block:: bat

            call alyvix_pybot C:\Python27\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\test.robot --outputdir C:\alyvix_reports\test\
            pause

        .. image:: pictures/alyvix_script_01_test_cmd_output.png
