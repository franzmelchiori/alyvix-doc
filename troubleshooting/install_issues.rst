.. _install_issues:

**************
Install issues
**************


.. _install_issues-pypiwin32_module:

PyPIWin32 module
================

If you :ref:`install Alyvix <install>` and ``pypiwin32`` raises a red exception, you can fix your deployment:

    1. backup your test cases;

        ..

    2. uninstall ``pypiwin32``, ``pywin32`` and ``alyvix``:

        ``pip uninstall pypiwin32``

        ``pip uninstall pywin32``

        ``pip uninstall alyvix``

    3. install ``alyvix`` and its dependencies:

        ``pip install alyvix``
