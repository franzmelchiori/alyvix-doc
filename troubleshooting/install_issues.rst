.. _install_issues:

**************
Install issues
**************


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
