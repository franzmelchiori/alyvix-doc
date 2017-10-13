.. _install_with_internet:

*********************
Install with Internet
*********************


If your probe can reach Internet through Command Prompt, you can install Alyvix thanks to ``conda`` that takes care about its version and dependencies.

    1. Install Anaconda

        * browse https://www.continuum.io/downloads and download **Anaconda 5.0.0 installer**, **strictly based on Python 2.7**, **for Windows 64bit**

        * run Anaconda installer (e.g. ``Anaconda2-5.0.0-Windows-x86_64.exe``) **as administrator**, installing Anaconda **for all users**

            .. image:: pictures/anaconda_5-0-0_install_01.PNG

        ..

          in ``C:\Anaconda2``

            .. image:: pictures/anaconda_5-0-0_install_02.PNG

        ..

          and adding Anaconda to the system PATH environment variable

            .. image:: pictures/anaconda_5-0-0_install_03.PNG

    2. Install Alyvix ``conda`` package

        * run Command Prompt **as administrator** and execute the following command to fetch and install the last Alyvix master release together with its Windows service:

            ``conda install -c https://conda.anaconda.org/alyvix alyvix``
