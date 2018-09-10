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

Imagine that your test case has to **wait for a login form** as follows and then it has to **fill the form with username and password** to proceed:

    .. image:: pictures/common_transactions/fill-login-forms_wuerthphoenix_citrix_login.png

You could build an Alyvix :ref:`Rect Finder <visual_keywords-rect_finder>` keyword: it will **measure how much the browser takes to render the login form**; then it will **fill the form and click on the Log On button** to access the service.

The ``wp_citrix_login_run`` keyword could be a :ref:`Rect Finder <visual_keywords-image_finder>` which is made as follows:

    .. image:: pictures/common_transactions/fill-login-forms_wuerthphoenix_citrix_login_build.png

..

    .. image:: pictures/common_transactions/fill-login-forms_wuerthphoenix_citrix_login_build_02.png

**Build the keyword** and **set the password** as described in the :ref:`encryption tool <encryption-tool_alyvix-how_to_use_encrypted_passwords>` section.

Import the :ref:`test case library <testcase_editor-basic_operations>` (only one time per test, after a visual keyword creation) and use ``wp_citrix_login_run`` simply as follows:

    .. image:: pictures/common_transactions/fill-login-forms_wuerthphoenix_citrix_login_build_03.png


.. _common_transactions-browse_menus_tabs:

Browse menus and tabs
=====================

Imagine that your test case has to **select a tab** (or **a menu**) **with a certain name** as follows:

    .. image:: pictures/common_transactions/menu_tab_select_visittrentino_homepage.png

You could build an Alyvix :ref:`Object Finder <visual_keywords-object_finder>` keyword, made of an :ref:`Image Finder <visual_keywords-image_finder>` as main component and a :ref:`Text Finder <visual_keywords-text_finder>` as sub component. The **image component** should include the **close button**, which is present **on each tab**, as the main component and some **fixed icons**, which are always shown **in the bar** below, as sub components to disambiguate the detection.

    .. image:: pictures/common_transactions/menu_tab_select_visittrentino_homepage_build.png

The **text component** should include all the **available space for text in a tab** as its :ref:`ROI <visual_keywords-text_definition>`. Set an :ref:`argument <visual_keywords-name_components>` to enable the selection of a **certain tab with a given name**.

    .. image:: pictures/common_transactions/menu_tab_select_visittrentino_homepage_build_02.png

..

    .. image:: pictures/common_transactions/menu_tab_select_visittrentino_homepage_build_03.png

Join the image and text components in an :ref:`Object Finder <visual_keywords-object_finder>`.

    .. image:: pictures/common_transactions/menu_tab_select_visittrentino_homepage_build_04.png

Import the :ref:`test case library <testcase_editor-basic_operations>` (only one time per test, after a visual keyword creation) and use ``chrome_tab_select`` simply as follows:

    .. image:: pictures/common_transactions/menu_tab_select_visittrentino_homepage_build_05.png

Moreover if your test case has to **select a menu item in a fixed position**, you could build an Alyvix :ref:`Image Finder <visual_keywords-image_finder>` with **two interaction on the same selected element** (i.e. the menu button): a **first click** to **expand the menu** and a **second displaced click** to **select the menu item**.

    .. image:: pictures/common_transactions/menu_tab_open_visittrentino_homepage_build.png

..

    .. image:: pictures/common_transactions/menu_tab_open_visittrentino_homepage_build_02.png

Import the :ref:`test case library <testcase_editor-basic_operations>` (only one time per test, after a visual keyword creation) and use ``chrome_window_open`` simply as follows:

    .. image:: pictures/common_transactions/menu_tab_open_visittrentino_homepage_build_03.png
