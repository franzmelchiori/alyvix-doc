.. _install_issues:

**************
Install issues
**************


.. _install_issues-pywin32_module:

PyWin32 module
==============

In case you are **installing Alyvix** on a distribution of **Anaconda older than the 5.0.0 version** (e.g. 4.4.0), :ref:`RIDE<testcase_editor-basic_operations>` could rise an **error about the win32ui module**.

    .. code-block:: bat

        Traceback (most recent call last):
          File "C:\Anaconda2\lib\site-packages\alyvix\robotproxy\alyvixlib.py", line 22, in <module>
            from alyvixcommon import *
          File "C:\Anaconda2\lib\site-packages\alyvix\robotproxy\alyvixcommon.py", line 25, in <module>
            from alyvix.devices.keyboard import KeyboardManager
          File "C:\Anaconda2\lib\site-packages\alyvix\__init__.py", line 22, in <module>
            from alyvix.tools.info import InfoManager
          File "C:\Anaconda2\lib\site-packages\alyvix\tools\info.py", line 22, in <module>
            from alyvix.tools.screen import ScreenManager
          File "C:\Anaconda2\lib\site-packages\alyvix\tools\screen\__init__.py", line 31, in <module>
            from windows import ScreenManager
          File "C:\Anaconda2\lib\site-packages\alyvix\tools\screen\windows.py", line 24, in <module>
            import win32ui

The solution is **install the PyWin32 package**:

    1. download ``pywin32-221.win-amd64-py2.7.exe`` `here <https://sourceforge.net/projects/pywin32/files/pywin32/Build%20221/pywin32-221.win-amd64-py2.7.exe/download>`_;

    2. run ``pywin32-221.win-amd64-py2.7.exe`` to install the **PyWin32 build 221**.


.. _install_issues-sip_module:

SIP module
==========

In case you are **installing Alyvix 2.5.1** on a distribution of **Anaconda older than the 4.4.0 version** (e.g. 4.2.0), :ref:`RIDE<testcase_editor-basic_operations>` could rise an **error about the SIP module**.

That is because of an Anaconda issue in managing its SIP package: for Anaconda the package seems up to date, but for Python is not.

    .. code-block:: bat

        C:\Windows\system32>conda install sip
        Fetching package metadata ...........
        Solving package specifications: .

        # All requested packages already installed.
        # packages in environment at C:\Anaconda2:
        #
        sip                       4.18                     py27_0

        C:\Windows\system32>python
        Python 2.7.12 |Anaconda 4.2.0 (64-bit)| (default, Jun 29 2016, 11:07:13) [MSC v.
        1500 64 bit (AMD64)] on win32
        Type "help", "copyright", "credits" or "license" for more information.
        Anaconda is brought to you by Continuum Analytics.
        Please check out: http://continuum.io/thanks and https://anaconda.org
        >>> import sip
        >>> sip.SIP_VERSION_STR
        '4.15.5'
        >>> exit()

The solution is **reinstall the SIP Anaconda package** with the following commands at the prompt:

    1. ``conda uninstall sip``;

    2. ``conda install sip``.
