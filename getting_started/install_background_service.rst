.. _install_background_service:

**************************
Install background service
**************************


Alyvix Background Service is a Windows Service and provides a way to keep active a graphical session of Windows. It manages a customizable RDP connection with one Windows session, continuously trying to sign in it.

    1. Install the service

        * download the `background service archive <http://alyvix.com/doc/alyvix_background_service_v20180101.zip>`_ ``alyvix_background_service_v20180101.zip``

        * unzip the background service files form the archive ``alyvix_background_service_v20180101.zip`` using the **archive password** that has been provided to you

        * run ``setup.exe`` as **admin**

            .. image:: pictures\alyvix_background_service_install_01.PNG

        ..

        * set the destination folder as ``C:\Program Files\Alyvix\Alyvix Background Service\`` and allow its use for **everyone**

        * wait the successful end of install

    2. Encrypt the password

        * browse the local folder ``C:\Program Files\Alyvix\Alyvix Background Service\``

        * run ``CryptoUtility.exe``

              .. image:: pictures\alyvix_background_service_encrypt_01.PNG

        ..

        * type ``k`` to set a **private key**

        * type ``e`` to encrypt the password of the Windows session for Alyvix

        * copy the **encrypted password**

        * type ``q`` to exit the program

    3. Setup the service

        * browse the local folder ``C:\Program Files\Alyvix\Alyvix Background Service\``

        * edit ``AlyvixBackgroundService.exe.config``

        * type the **session credentials** of the Alyvix session in ``<add key="user" value="DOMAIN\USERNAME"/>`` (e.g. ``blatech\alyvix``)

        * paste the **encrypted password** of the Alyvix session in ``<add key="password" value="PASSWORD"/>`` (e.g. ``rEsQYSqskAdpWnm7a9Azxg==``)

        * set the **width resolution** of the Alyvix machine ``<add key="width" value="WIDTH_RESOLUTION"/>`` (e.g. ``1280``)

        * set the **height resolution** of the Alyvix machine ``<add key="height" value="HEIGHT_RESOLUTION"/>`` (e.g. ``800``)

    4. Run the service

        * run Windows Services ``services.msc``

        * set the **startup type** of the Alyvix Background Service as ``Automatic``

              .. image:: pictures\alyvix_background_service_install_02.PNG

        ..

        * restart the service
