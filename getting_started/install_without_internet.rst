.. _install_without_internet:

************************
Install without Internet
************************


If your probe can **NOT** reach Internet through Command Prompt.. do not worry! You can install Alyvix anyway, moving on the probe the 2 necessary ingredients: Anaconda installer and Alyvix ``conda`` package.

    1. Install Anaconda

        * move **Anaconda 5.0.0 installer** from an Internet connected machine: browse https://www.continuum.io/downloads and download **Anaconda 5.0.0 installer**, **strictly based on Python 2.7**, **for Windows 64bit**

        * run Anaconda installer (e.g. ``Anaconda2-5.0.0-Windows-x86_64.exe``) **as administrator**, installing Anaconda **for all users**

            .. image:: pictures/anaconda_5-0-0_install_01.PNG

        ..

          in ``C:\Anaconda2``

            .. image:: pictures/anaconda_5-0-0_install_02.PNG

        ..

          and adding Anaconda to the system PATH environment variable

            .. image:: pictures/anaconda_5-0-0_install_03.PNG

    2. Install Alyvix ``conda`` package

        * move Alyvix archive from an Internet connected machine: browse https://anaconda.org/alyvix/alyvix/files and download the last **main** release of the Alyvix ``conda`` package (e.g. ``alyvix-2.5.2-py27h47b0408_1.tar.bz2``)

            https://anaconda.org/alyvix/alyvix/2.5.2/download/win-64/alyvix-2.5.2-py27h47b0408_1.tar.bz2

        * run Command Prompt **as administrator** and execute the following command to install Alyvix (in the folder where the archive file is stored) together with its Windows service:

            ``conda install --offline alyvix-2.5.2-py27h47b0408_1.tar.bz2``
