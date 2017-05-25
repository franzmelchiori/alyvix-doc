*********************
Install with Internet
*********************

If your probe can reach Internet through Command Prompt, you can install Alyvix thanks to ``conda`` that takes care about its version and dependencies.

  1. Install Anaconda

    * download Anaconda installer, browsing https://www.continuum.io/downloads and strictly clicking the version based on Python 2.7 for Windows 64bit

    * run Anaconda installer (e.g. ``Anaconda2-x.x.x-Windows-x86_64.exe``) **as administrator**, installing Anaconda **for all users** and right in ``C:\Anaconda2``

  2. Install Alyvix ``conda`` package

    * run Command Prompt **as administrator** and execute the following command to fetch and install the last Alyvix master release together with its Windows service:

      ``conda install -c https://conda.anaconda.org/alyvix alyvix``
