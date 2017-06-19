.. _commandline_output:

*******************
Command line output
*******************


After the execution of an Alyvix :ref:`test case script<commandline_scripting>`, the **output message** is printed in the same **Command Prompt window**.

Example:

    .. image:: pictures/testcase_script_output.png

The first row shows:

    1. the **exit state of the test case** (i.e. the ``errorlevel`` of the test case: ``OK``, ``WARNING``, ``CRITICAL`` or ``UNKNOWN``);
    2. an **overall description of the test case outcome** (e.g. ``all steps are ok``, ``some error occurred, last filled perf data is <performance_name>``)
    3. the **transaction pipe with the test case transactions**; each transaction shows the following values:

        * **performance** (amount of seconds);
        * **warning threshold** (amount of seconds);
        * **critical threshold** (amount of seconds).

The other rows are the **list of the test case transactions**: each one shows its own **exit state** and its **performance**.

Example:

    .. code-block:: bat

        OK: all steps are ok|citrix_login_form_ready_02=0.000s;10.000;15.000;; citrix_login_form=3.000s;;;; citrix_storefront=1.459s;10.000;15.000;; outlook_firstpage=15.322s;20.000;25.000;; outlook_emptyfolder_run=0.258s;5.000;7.500;; outlook_newemail=0.814s;10.000;15.000;; outlook_email_delivered=1.603s;15.000;40.000;; outlook_closed=1.091s;30.000;40.000;; citrix_storefront_menu=0.106s;5.000;7.500;; citrix_storefront_logoff=0.461s;10.000;15.000;;
        OK: citrix_login_form_ready_02 time is 0.000 sec.
        OK: citrix_login_form time is 3.000 sec.
        OK: citrix_storefront time is 1.459 sec.
        OK: outlook_firstpage time is 15.322 sec.
        OK: outlook_emptyfolder_run time is 0.258 sec.
        OK: outlook_newemail time is 0.814 sec.
        OK: outlook_email_delivered time is 1.603 sec.
        OK: outlook_closed time is 1.091 sec.
        OK: citrix_storefront_menu time is 0.106 sec.
        OK: citrix_storefront_logoff time is 0.461 sec.
