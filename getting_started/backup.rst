.. _backup:

******
Backup
******


*1 test case* is made by *4 ingredients*:

    * ``C:\Python27\Lib\site-packages\alyvix\robotproxy\AlyvixProxy<test_case_name>.py``
    * ``C:\Python27\Lib\site-packages\alyvix\robotproxy\Alyvix<test_case_name>Objects_extra\``
    * ``C:\Python27\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\<test_case_name>.robot``
    * ``C:\Python27\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\Alyvix<test_case_name>Objects\``

    .. note::
        It is recommended to save your test cases in ``C:\Python27\Lib\site-packages\alyvix\robotproxy\alyvix_testcases\``.

In this context, you can **backup all your test cases** as follows:

    1. copy ``C:\Python27\Lib\site-packages\alyvix\robotproxy\`` in your backup folder, e.g. ``C:\alyvix_backups\robotproxy_backup_<date>\``
    2. delete ``alyvixlib.py`` and ``alyvixcommon.py`` from ``C:\alyvix_backups\robotproxy_backup_<date>\``

    .. warning::
        This latter step is important to avoid overwriting later versions of the main Alyvix modules when you restore the backup.

Vice versa, you can **restore a backup** copying the content of ``C:\alyvix_backups\robotproxy_backup_<date>\`` in ``C:\Python27\Lib\site-packages\alyvix\robotproxy\``.
