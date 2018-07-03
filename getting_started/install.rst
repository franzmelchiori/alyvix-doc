.. _install:

*******
Install
*******


Your Alyvix probe must satisfy the :ref:`system requirements<system_requirements>` and be connected to the Internet.

    1. Install Python

        * download `Python 2.7.15 64bit Windows installer <https://www.python.org/ftp/python/2.7.15/python-2.7.15.amd64.msi>`_

        * run ``python-2.7.15.amd64.msi`` **as administrator**

            install Python **for all users**

                .. image:: pictures/python_2-7-15_install_01.PNG

            ..

            in ``C:\Python27``

                .. image:: pictures/python_2-7-15_install_02.PNG

            ..

            and add ``python.exe`` to the system PATH environment variable

                .. image:: pictures/python_2-7-15_install_03a.PNG

            ..

    2. Install Alyvix ``pip`` package

        * run Command Prompt **as administrator**

        * execute the following command to fetch and install the last Alyvix master release and its dependencies:

            ``pip install alyvix``

        .. warning::
            If ``pypiwin32`` raises a red exception, :ref:`fix your deployment <install_issues-pypiwin32_module>`.

        .. note::
            ``pip`` is now the only package manager for Alyvix. ``conda`` has been deprecated.
