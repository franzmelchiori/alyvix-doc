.. _common_transactions:

*******************
Common transactions
*******************


.. _common_transactions-look_and_click:

Look and click
==============

Imagine that your test case has to **wait for the arrow button and the main logo** of the following webpage and then it has to **click on the arrow button** to proceed.

    .. image:: pictures/common_transactions/look-and-click_visittrentino_homepage.png

You could build an Alyvix :ref:`Image Finder <visual_keywords-image_finder>` keyword: it will **measure how much the browser takes to render the button and the logo**; then it will **click on the button** to move on.

The ``vt_homepage_ready`` keyword could be an :ref:`Image Finder <visual_keywords-image_finder>` which is made as follows:

    .. image:: pictures/common_transactions/look-and-click_visittrentino_homepage_build.png

..

    .. image:: pictures/common_transactions/look-and-click_visittrentino_homepage_build_02.png

Import the :ref:`test case library <testcase_editor-basic_operations>` (only one time per test, after a visual keyword creation) and use ``vt_homepage_ready`` simply as follows:

    .. image:: pictures/common_transactions/look-and-click_visittrentino_homepage_build_03.png


.. _common_transactions-fill_login_forms:

Fill login forms
================

Imagine that your test case has to **wait for a login form** as follows and then it has to **fill the form with username and password** to proceed.

    .. image:: pictures/common_transactions/fill-login-forms_wuerthphoenix_citrix_login.png

You could build an Alyvix :ref:`Rect Finder <visual_keywords-rect_finder>` keyword: it will **measure how much the browser takes to render the login form**; then it will **fill the form and click on the Log On button** to access the service.

The ``wp_citrix_login_run`` keyword could be a :ref:`Rect Finder <visual_keywords-image_finder>` which is made as follows:

    .. image:: pictures/common_transactions/fill-login-forms_wuerthphoenix_citrix_login_build.png

**Build the keyword** and **set the password** as described in the :ref:`encryption tool <encryption-tool_alyvix-how_to_use_encrypted_passwords>` section.

Import the :ref:`test case library <testcase_editor-basic_operations>` (only one time per test, after a visual keyword creation) and use ``wp_citrix_login_run`` simply as follows:

    .. image:: pictures/common_transactions/fill-login-forms_wuerthphoenix_citrix_login_build_02.png
