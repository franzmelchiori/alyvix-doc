************************
Install without Internet
************************

If your probe can NOT reach Internet through Command Prompt.. do not worry! You can install Alyvix anyway, moving on the probe the three necessary ingredients: Anaconda installer, PyQt, Pillow and Alyvix conda packages.

  1. Install Anaconda

    - move Anaconda installer from an Internet connected machine: download Anaconda installer, browsing https://www.continuum.io/downloads and strictly clicking the version based on Python 2.7 for Windows 64bit

    - run Anaconda installer (e.g. Anaconda2-4.3.1-Windows-x86_64.exe) as administrator, installing Anaconda for all users and right in C:\Anaconda2

  2. Install PyQt (conda package)

    - move PyQt archive from an Internet connected machine: download PyQt conda package, browsing https://repo.continuum.io/pkgs/free/win-64/ and strictly clicking the 2.7.1 version based on Python 2.7.1 for Windows 64bit (pyqt-4.10.4-py27_1.tar.bz2)

      https://repo.continuum.io/pkgs/free/win-64/pyqt-4.10.4-py27_1.tar.bz2

    - rename the filename:

      pyqt-4.10.4-py27_1.tar.bz2

    - run Command Prompt as administrator and execute the following command to install PyQt:

      <path_to_pillow_archive>\conda install --offline pyqt-4.10.4-py27_1.tar.bz2

  3. Install Pillow (conda package)

    - move Pillow archive from an Internet connected machine: download Pillow conda package, browsing https://anaconda.org/anaconda/pillow/files and strictly clicking the 2.7.0 version based on Python 2.7.0 for Windows 64bit (win-64-pillow-2.7.0-py27_0.tar.bz2)

      https://anaconda.org/anaconda/pillow/2.7.0/download/win-64/pillow-2.7.0-py27_0.tar.bz2

    - rename the filename:

      pillow-2.7.0-py27_0.tar.bz2

    - run Command Prompt as administrator and execute the following command to install Pillow:

      <path_to_pillow_archive>\conda install --offline pillow-2.7.0-py27_0.tar.bz2

  4. Install Alyvix (conda package)

    - move Alyvix archive from an Internet connected machine: download Alyvix conda package, browsing https://anaconda.org/alyvix/alyvix/files and clicking on the last main release (alyvix-2.4.1-py27_1.tar.bz2)

      https://anaconda.org/alyvix/alyvix/2.4.1/download/win-64/alyvix-2.4.1-py27_1.tar.bz2

    - rename the filename:

      alyvix-2.4.1-py27_1.tar.bz2

    - run Command Prompt as administrator and execute the following command to install Alyvix together with its Windows service:

      <path_to_alyvix_archive>\conda install --offline alyvix-2.4.1-py27_1.tar.bz2
