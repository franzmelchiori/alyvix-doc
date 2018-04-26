.. _encryption_tool:

***************
Encryption tool
***************


.. _encryption-tool_alyvix-crypto-utility:

Alyvix Crypto Utility
=====================

*Alyvix Crypto Utility* is a **command line tool to encrypt text strings as passwords**. You can use it as follows:

    * browse the local folder ``C:\Python27\Scripts\``;

    * run ``alyvix_crypto_utility.bat``:

          .. image:: pictures/alyvix_crypto_utility.png

    ..

    * type ``k`` to set a **private key** (type ``y`` to confirm);

    * type ``e`` to **encrypt a password**;

    * highlight the **encrypted password** with the mouse

    * press ``enter`` to copy the encrypted password;

    * type ``q`` to **exit the program**.

.. warning::
    The encryption mechanism is strictly related to the (virtual) machine on which it runs: **if you** :ref:`port a test case <backup>` **on another probe, you must newly encrypt text strings as passwords on the new machine**.


.. _encryption-tool_alyvix-how_to_use_encrypted_passwords:

How to use encrypted passwords
------------------------------

**Encrypted passwords can be used through** :ref:`visual keywords <visual_keywords-name_components>`, which **decrypt them in runtime**. So that, ``.robot`` :ref:`test cases <testcase_editing>` **do not contains clear text passwords**, but just encrypted ones. You can use an encrypted password in a visual keyword as follows:

    * build a :ref:`visual keyword <visual_keywords>` to fill a login form; for example, you could **build** a ``login_fill`` :ref:`rect finder <visual_keywords-rect_finder>`:

              .. image:: pictures/login_form_build_01.gif

        ..

    * ``login_fill`` :ref:`rect finder <visual_keywords-rect_finder>` could be **made of 3 properly defined** :ref:`components <visual_keywords-rect_definition>`:

            .. image:: pictures/login_form_build_02.png

        ..

    * **set 2** :ref:`arguments <visual_keywords-name_components>`:

          .. image:: pictures/login_form_build_02b.png

    ..

    * **set click** as :ref:`interaction setting <visual_keywords-interaction_settings>` for the **main component** (i.e. the username text box), **type** ``arg1`` in the **interaction text box** and **uncheck Quotes** (it is the reference name of a keyword argument, it is not a regular text string):

          .. image:: pictures/login_form_build_02ca.png

    ..

    * **set click** as :ref:`interaction setting <visual_keywords-interaction_settings>` for the **first subcomponent** (i.e. the password text box), **type** ``arg2`` in the **interaction text box**, **uncheck Quotes** and **check Encrypted** (we are going to pass an :ref:`encrypted argument <encryption-tool_alyvix-crypto-utility>` to the keyword):

          .. image:: pictures/login_form_build_02cb.png

    ..

    * **set click** as :ref:`interaction setting <visual_keywords-interaction_settings>` for the **second subcomponent** (i.e. the confirm button);

    ..

    * **use** ``login_fill`` in the :ref:`test case <testcase_editor-basic_operations>` as follows:

        +----------------+----------------+--------------------------+
        | ``login_fill`` | ``<username>`` | ``<encrypted_password>`` |
        +----------------+----------------+--------------------------+

    * **run** the :ref:`test case <testcase_editor-basic_operations>` and ``login_fill`` will be able to **solve the login form**:

          .. image:: pictures/login_form_build_03.gif

    ..
