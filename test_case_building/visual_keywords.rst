.. _visual_keywords:

***************
Visual keywords
***************


.. _visual_keywords-keyword_definition:

Keyword definition
==================

The :ref:`Alyvix button <testcase_editor-editor_buttons>` opens the **selector of visual keywords** (that has been previously defined by the user) for the current test case (e.g. ``alyvix_website``, so that its keyword library would be ``AlyvixProxyalyvix_website`` ``.py``). The selector shows the name and the type of each keyword: *[IF]* means :ref:`Image Finder <visual_keywords-image_finder>`, *[RF]* means :ref:`Rect Finder <visual_keywords-rect_finder>`, *[TF]* means :ref:`Text Finder <visual_keywords-text_finder>` and *[OF]* stays for :ref:`Object Finder <visual_keywords-object_finder>`.

.. note::
    *Imported keywords* from other *Alyvix test case libraries* (e.g. ``citrix_outlook``, so that its keyword library would be ``AlyvixProxycitrix_outlook`` ``.py``) are *not* listed in the selector window. You can edit keywords in a certain test case library just opening that test case

..

    .. image:: pictures/ride_05a_keyword_selector.png

The *New* button opens the selector of :ref:`Alyvix Finders <visual_keywords-alyvix_finders>`. The *Edit* button brings to the Finder dialog of the selected keyword, in order to modify its properties (e.g. component selections and region of interests, detection and interaction settings, performance thresholds). The *Remove* button deletes the selected keywords or, in case of :ref:`Object Finder <visual_keywords-object_finder>` keywords, crumbles them into its basic components (IF, RF, TF).

    .. image:: pictures/ride_05b_finder_selector.png

The selector of the :ref:`Alyvix Finders <visual_keywords-alyvix_finders>` allows you to select the type (image, rectangle, text, object) of a new keyword to define. The ``Delay`` spin control delays of a given amount of seconds the subsequent selection of components on screen. The graphic definition a visual keyword freezes your screen, in order to select components. Increase the delay if you need time to trigger a certain state of the screen (e.g. opening a menu in an app dialog).

Start defining a *visual keyword* means selecting its components on screen: one *main selection* is necessary, but then multiple *sub selections* are possible. Sub components are selected within their *region of interests*. The latter *ROI* are useful to link sub components to the main component. Each Alyvix Finder has a procedure to select its components and ROI. The important reasons for sub components and their ROI follow below. The detection of application transactions can be:

* more *complete*: GUI rendering could be element-by-element, so it could be necessary to detect several components to check a completed transaction; moreover, it is possible to interact with several GUI elements and not just with one;
* more *robust*: the same GUI element could be used twice, so it could be necessary to define a unique transaction selecting more components;
* more *flexible*: the same GUI element could be rendered in a different position, so it is necessary to link sub to main components through ROI; moreover, ROI are also useful to restrict the screen area to process, in order to filter out the rest and to save computation time.


.. _visual_keywords-image_definition:

Image Finder main and subs
--------------------------

    .. image:: pictures/ride_07a_if_main_sub.png

An example GUI shows three identical stars and a possible transaction could be to **interact with the third star**, which is left to the green sign.

Selecting just the third star as a main component of an :ref:`Image Finder <visual_keywords-image_finder>` is not enough. It would be an ambiguous transaction: the three stars have exactly the same aspect. Alyvix detects all the three stars and then interacts with the first one, because of the raster logic of the screen scanner.

To correctly define a unique keyword, it is necessary to **select the green sign as a sub component**. Remember that sub components of :ref:`Image Finder <visual_keywords-image_finder>` are selected within their ROI (region of interests). The upper left corner of ROI are linked with the upper left corner of the main component selection.

    .. image:: pictures/ride_07bb_if_main_sub.png

..

    1. Select the **main component** on the screen;
    2. select the **ROI of the sub component** 1 on the screen;
    3. select the **sub component** 1 within its ROI;
    4. eventually repeat 2. and 3. to add more sub components;
    5. press :kbd:`CTRL+O` to set the :ref:`IF keyword properties <visual_keywords-image_finder>`.

    .. image:: pictures/image_finder_selection.gif

.. note::
    It is possible to **unlimited extend ROI boundaries** towards one or more directions pressing :kbd:`ARROWS` and **undo selections** with :kbd:`CTRL+Z`.


.. _visual_keywords-rect_definition:

Rect Finder main and subs
-------------------------

    .. image:: pictures/ride_07c_rf_main_sub.png

An example GUI shows three identical text boxes and a possible transaction could be **interacting with the third text box**, which is left to the *OK* button.

Selecting just the third text box as a main component of an :ref:`Rect Finder <visual_keywords-rect_finder>` is not enough. It would be an ambiguous transaction: the three text boxes have exactly the same aspect. Alyvix detects all the three text boxes and then interacts with the first one, because of the raster logic of the screen scanner.

To correctly define a unique keyword, it is necessary to **select the OK button as a sub component**. Remember that sub components of :ref:`Rect Finder <visual_keywords-rect_finder>` are selected within their ROI (region of interests). The upper left corner of ROI are linked with the upper left corner of the main component selection.

    .. image:: pictures/ride_07db_rf_main_sub.png

..

    1. Select the **main component** on the screen;
    2. select the **ROI of the sub component** 1 on the screen;
    3. select the **sub component** 1 within its ROI;
    4. eventually repeat 2. and 3. to add more sub components;
    5. press :kbd:`CTRL+O` to set the :ref:`RF keyword properties <visual_keywords-rect_finder>`.

    .. image:: pictures/rect_finder_selection.gif

.. note::
    It is possible to **unlimited extend ROI boundaries** towards one or more directions pressing :kbd:`ARROWS` and **undo selections** with :kbd:`CTRL+Z`.


.. _visual_keywords-text_definition:

Text Finder main and subs
-------------------------

    .. image:: pictures/ride_07e_tf_main_sub.png

An example GUI shows three identical "Name" text strings and a possible transaction could be **interacting with the third "Name" text string**, which is left to the "Franz" text string.

Selecting just the "Name" text string as a main component of a :ref:`Text Finder <visual_keywords-text_finder>` is not enough. It would be an ambiguous transaction: the three "Name" text string have exactly the same aspect. Alyvix detects all the three "Name" text strings and interacts with the first one, because of the raster logic of the screen scanner.

To correctly define a unique keyword, it is necessary to **select the "Franz" text string as a sub component**. Remember that all the :ref:`Text Finder <visual_keywords-text_finder>` component selections, especially for the main component, lie in their ROI (region of interests) and the upper left corner of ROI are linked with the upper left corner of the screen. That differs from the :ref:`Image Finder <visual_keywords-image_finder>` and :ref:`Rect Finder <visual_keywords-rect_finder>`: in these cases the main component selection is defined within the entire screen.

.. warning::
    The main component of a :ref:`Text Finder <visual_keywords-text_finder>` is going to be searched within its ROI and not on the entire screen. This is the reason why a :ref:`Text Finder <visual_keywords-text_finder>` **should be only used as sub components of Object Finders**.

..

    .. image:: pictures/ride_07fb_tf_main_sub.png

..

    1. Select the **ROI of the main component** on the screen;
    2. select the **main component** within its ROI;
    3. select the **ROI of the sub component** 1 on the screen;
    4. select the **sub component** 1 within its ROI;
    5. eventually repeat 3. and 4. to add more sub components;
    6. press :kbd:`CTRL+O` to set the :ref:`TF keyword properties <visual_keywords-text_finder>`.

    .. image:: pictures/text_finder_selection.gif

.. note::
    It is possible to **unlimited extend ROI boundaries** towards one or more directions pressing :kbd:`ARROWS` and **undo selections** with :kbd:`CTRL+Z`.


.. _visual_keywords-object_definition:

Object Finder main and subs
---------------------------

    .. image:: pictures/ride_07g_of_main_sub.png

An example GUI shows three identical stars and a possible transaction could be **interacting with the third star**, left to the "Franz" text string.

Selecting just the third star as a main component of an :ref:`Image Finder <visual_keywords-image_finder>` is not enough. It would be an ambiguous transaction: the three stars have exactly the same aspect. Alyvix detects all the three stars and then interacts with the first one, because of the raster logic of the screen scanner.

To correctly define a unique keyword, it is necessary to **select the green sign as a sub component**. Remember that sub components of :ref:`Image Finder <visual_keywords-image_finder>` are selected within their ROI (region of interests). The upper left corner of ROI are linked with the upper left corner of the main component selection.

To correctly define a unique keyword, it is necessary to **select the "Franz" text string as a sub component**. Firstly, define the star as an :ref:`Image Finder <visual_keywords-image_finder>` and the "Franz" text string as a :ref:`Text Finder <visual_keywords-text_finder>`. Secondly, select them as the main and a sub component of an :ref:`Object Finder <visual_keywords-object_finder>` defining the ROI (region of interest) around the sub component to link it to the main component.

.. note::
    The most common and useful **Object Finder combinations** are **IF+TF** and **RF+TF**.

..

    .. image:: pictures/ride_07hb_of_main_sub.png

..

    1. Select the **main component**;
    2. select the **sub component** 1;
    3. select the **ROI of the sub component** 1 on the screen;
    4. eventually repeat 2. and 3. to add more sub components;
    5. press :kbd:`CTRL+O` to set the :ref:`OF keyword properties <visual_keywords-object_finder>`.

    .. image:: pictures/object_finder_selection.gif

.. note::
    It is possible to **unlimited extend ROI boundaries** towards one or more directions pressing :kbd:`ARROWS` and **undo selections** with :kbd:`CTRL+Z`.


.. _visual_keywords-name_components:

Name, arguments and components
------------------------------

After having :ref:`visually define a keyword <visual_keywords-image_definition>`, the first thing to do is to insert the **keyword name** in the *Name* text box. The best practice is to type **in lowercase**, **with underscores**, **no spaces** and structured as follows: ``<application name>_<transaction name>_<transaction state>`` (e.g. ``citrix_loginform_ready``, ``ax12_dynamicsax_closed``). Append the ``_<keyword type>`` if you plan to use the keyword in an :ref:`Object Finder <visual_keywords-object_finder>`.

You can declare a number of **argument variables as the keyword inputs**. You can then type ``arg1``, ``arg2``, etc. in the :ref:`interaction text box <visual_keywords-interaction_settings>` of main and sub components. Alyvix will run the keyword taking its **arguments from the test case editor**: in the cells on the right (from where you insert the keyword name) you can type its **arguments as text strings**.

    .. image:: pictures/ride_11a_alyvix_2-4-1_gui_name.png

Type the keyword name (and eventually its arguments) in your test case:

    +---------------------------+
    | ``<visual_keyword_name>`` |
    +---------------------------+

    or

    +---------------------------+-------------------+-------------------+--------+
    | ``<visual_keyword_name>`` | ``<arg1_string>`` | ``<arg2_string>`` | ``..`` |
    +---------------------------+-------------------+-------------------+--------+

Example:

    1. Type the *keyword name* and set the amount of its *arguments* in the Alyvix Finder dialog:

    ..

        .. image:: pictures/ride_11ac_alyvix_2-4-1_gui_arg.png

    2. Type ``arg1``, ``arg2``, etc. (i.e. if you have set a number of arguments) in the :ref:`interaction text box <visual_keywords-interaction_settings>` or in the :ref:`detection text box <visual_keywords-text_finder>` in case of a Text Finder:

    ..

        .. image:: pictures/ride_11ad_alyvix_2-4-1_gui_arg.png

    ..

        .. warning::
            Untick *Quotes* if you use keyword arguments. Moreover, tick *Encrypted* if you use encrypted keyword arguments. You can encrypt strings with the :ref:`Alyvix encryption tool <encryption_tool>`.

    3. Type the *keyword name* (and eventually its arguments) in your test case:

    ..

        .. image:: pictures/ride_11ab_alyvix_2-4-1_gui_name.png

In the left pane of the dialog there are all the **components** previously selected on screen: tick (or untick) them to visualize (or not) their *selection* and *ROI* (region of interests) on screen. Click on each component to set its own detection and interaction properties.

    .. image:: pictures/ride_11b_alyvix_2-4-1_gui_components.png


.. _visual_keywords-detection_settings:

Detection settings
------------------

In the detection section of each *Alyvix Finder*, you can select 2 **detection modes**: *Appeared* and *Disappeared*. When a keyword will be executed, its mode affects the way Alyvix will detect it (i.e. the visual elements of transaction) and report its performances.

    .. image:: pictures/ride_11c_alyvix_2-4-1_gui_detection.png

Selecting **Appeared**, Alyvix continuously tries and retries to detect the graphic elements on screen at a certain pace (by default this period is 0.5s, but it is customizable thanks to the system keywords :ref:`Alyvix Config <system_keywords-debug_keywords-alyvix_config>` and :ref:`Set Alyvix Info <system_keywords-debug_keywords-set_alyvix_info>`). That continues until the *Timeout* threshold will be reached: if the **Break** option is ticked, then the keyword breaks the test case, otherwise it returns ``False`` and lets the test to proceed. The latter option could be useful in case of transactions that not always happen (e.g. to manage popups).

On the other hand, **Disappeared** allows to detect the disappearance of graphic elements of screen (e.g. disappearance of an hourglass icon at the end of a loading).

The **Performance** check box enables or disables the performance measurement:

    1. :ref:`Add Perfdata <system_keywords-performance_keywords-add_perfdata>` declares the keyword performance
    2. if the *Performance* setting is ticked, the keyword outputs its performance (with 0.1s of accuracy and 0.001s of precision)
    3. :ref:`Print Perfdata <system_keywords-performance_keywords-print_perfdata>` collects and prints out all the available performance from the test case

In the *Warning* and *Critical* text boxes you can set the amount of seconds of these thresholds.

    .. image:: pictures/performance_thresholds.png


.. _visual_keywords-interaction_settings:

Interaction settings
--------------------

In the interaction section of each *Alyvix Finder*, you can set an **interaction mode** for the :ref:`selected main or sub component <visual_keywords-name_components>` of the keyword that you are defining.

    .. image:: pictures/ride_11d_alyvix_2-5-2_gui_interaction.png

Selecting **Click** or **Right Click**, Alyvix will bring the mouse pointer over the detected component and press the left or the right button of the mouse. It is possible to set the number of *Clicks* and adjust *Delays* as the amount of milliseconds between clicks.

You can also set an *Interaction Point* in order to click somewhere else from the center of the component: click on the *Interaction Point* button, set the point (continuously) clicking on the screen and press :kbd:`CTRL+O` to confirm.

    .. image:: pictures/ride_11db_alyvix_2-4-1_gui_interaction.png

Click on the *Reset Point* button to reset the interaction point at the center of the component.

    .. image:: pictures/ride_11dc_alyvix_2-4-1_gui_interaction.png

**Hold'n'Release** is useful to drag'n'drop or slide GUI elements. There are 6 modes that you can select from the drop-down list on the right. The keyword execution will work as follows:

    * *Hold*: the pointer will press and hold the component;
    * *Release*: the pointer will release over the component;

    ..

        .. image:: pictures/hold_release.gif

    ..

        .. note::
            To drag'n'drop a GUI element (look at the example above) it is necessary to set the *Hold* mode for **a target component** (e.g. file icon) and the *Release* mode for **another destination component** (e.g. folder icon)

    * *Release Up*: the pointer will press and hold the component, that will then be released towards up of an amount of pixels (to set in the spin box on the right);
    * *Release Down*: the pointer will press and hold the component, that will then be released towards down of an amount of pixels (to set in the spin box on the right);
    * *Release Left*: the pointer will press and hold the component, that will then be released towards left of an amount of pixels (to set in the spin box on the right);
    * *Release Right*: the pointer will press and hold the component, that will then be released towards right of an amount of pixels (to set in the spin box on the right).

    ..

        .. image:: pictures/release_displace.gif

For the latter 4 modes, select the amount of *pixel displacement* thanks to the spin box on the right: double click and insert the desired number of pixels as the release distance.

    .. image:: pictures/ride_11dd_alyvix_2-4-1_gui_interaction.png

**Move** will bring the mouse pointer over the detected component without pressing anything.

Selecting **None**, Alyvix will not interact with the component (the mouse pointer will not move or click anything).

At the bottom of the interaction section, **typing settings** take place. In the text box can be inserted text strings and shortcuts to send (e.g. ``bla``, most of the time after a *Click* interaction somewhere).

Regular text strings can be typed together with shortcuts (e.g. ``bla{enter}``). You can find a list of the most useful shortcuts in the description of :ref:`Send Keys <system_keywords-io_keywords-send_keys>` system keyword.

It is also possible to bring the :ref:`keyword arguments <visual_keywords-name_components>` as part of the keystrokes to send.

.. warning::
    Remember to untick *Quotes*, to add one more *Arguments* (clicking the up arrow of the spin box) and finally type just an argument variable (e.g. ``arg1``, ``arg2``, etc.).

It is even possible to bring strings, :ref:`shortcuts <system_keywords-io_keywords-send_keys>` and :ref:`arguments <visual_keywords-name_components>` all together (e.g. ``arg1+"bla{tab}"+arg2+"bla{enter}"``).

.. warning::
    Also in this case, remember to untick *Quotes* and to add one or more *Arguments*.

*Delays [ms]* sets the sleep intervals (in milliseconds) between keys. *Duration [ms]* sets how long (in milliseconds) keys are going to be pressed.


.. _visual_keywords-alyvix_finders:

Alyvix Finders
==============

The *Alyvix Finders* are the GUI tools to **visually define application transactions**. You can build *Alyvix visual keywords* with the Alyvix Finders. Finally, you can automate application transactions running Alyvix visual keywords in test cases. There are three Alyvix Finders, one for each **type of visual element to detect** on screen: images, rectangles and text. The *Object Finder* group together basic Alyvix Finders (IF, RF, TF) in order to detect and interact with **different types of visual elements** running one single keyword (e.g. a login form made of text boxes, their labels on a side and a brand logo in a corner).

After the :ref:`selection of an Alyvix Finder <visual_keywords-keyword_definition>` and the :ref:`selection of main and sub components <visual_keywords-image_definition>`, press :kbd:`CTRL+O` to **show the setting dialog**. The Image, Rect and Text Finders have in common most of their settings:

    * :ref:`Name and components <visual_keywords-name_components>`
    * :ref:`Detection settings <visual_keywords-detection_settings>`
    * :ref:`Interaction settings <visual_keywords-interaction_settings>`

The :ref:`Image Finder <visual_keywords-image_finder>` has its own similarity threshold, the :ref:`Rect Finder <visual_keywords-rect_finder>` has sizing thresholds and the :ref:`Text Finder <visual_keywords-text_finder>` has regular expression filters. The :ref:`Object Finder <visual_keywords-object_finder>` dialog is designed to link together the previous basic Alyvix Finders.


.. _visual_keywords-image_finder:

Image Finder
------------

*Image Finders* produce Alyvix visual keywords that are able to detect and interact with **images** (i.e. pixel matrixes). This is the *Image Finder* dialog:

    .. image:: pictures/ride_06a_image_finder.png

To define such keywords follow these steps:

    1. select the Image Finder in the :ref:`selector of visual keywords <visual_keywords-keyword_definition>`;
    2. select :ref:`main and sub components <visual_keywords-image_definition>` of the selected Finder;
    3. type the :ref:`keyword name <visual_keywords-name_components>` and eventually set the number of arguments;
    4. the *Image Finder* features a spin box to set the **visual likelihood threshold** for the selected component. You can set a number between 0 and 1, with two decimal places. The default value is ``0.70`` and it works just fine most of the cases;

        .. image:: pictures/ride_06ab_image_finder.png

    ..

        .. note::
            To **disambiguate graphical elements** in a transaction, it is better to **add more components** instead of increasing the visual likelihood threshold

    5. set the :ref:`detection properties <visual_keywords-detection_settings>`;
    6. set the :ref:`interaction properties <visual_keywords-interaction_settings>`;
    7. click the *OK* button to save the keyword.


.. _visual_keywords-rect_finder:

Rect Finder
-----------

*Rect Finders* produce Alyvix visual keywords that are able to detect and interact with **rectangles** (e.g. text boxes, rectangle buttons). This is the *Rect Finder* dialog:

    .. image:: pictures/ride_08_rect_finder.png

To define such keywords follow these steps:

    1. select the Rect Finder in the :ref:`selector of visual keywords <visual_keywords-keyword_definition>`;
    2. select :ref:`main and sub components <visual_keywords-rect_definition>` of the selected Finder;
    3. type the :ref:`keyword name <visual_keywords-name_components>` and eventually set the number of arguments;
    4. the *Rect Finder* features the controls to set the **allowed boundaries** of those rectangles that you want to detect;

        1. there are 2 modes to define valid rectangles: **Sizing** and **Tolerance** areas. Click on the radio button of one them;

        ..

            .. image:: pictures/rect_finder_tuning.gif

        ..

        2. tick the *Show* check box of the selected mode to see the ongoing tuning of valid rectangle areas;
        3. type integer numbers, click spin boxes or scroll mouse wheel to **tune the violet area** for the selected component. The rectangle contours on screen (or in region of interests for sub components) that fit into the allowed boundaries will be taken into account by Alyvix (i.e. during the keyword execution);

            .. image:: pictures/ride_08b_rect_finder.png

        ..

            .. note::
                 **Sizing** mode is generally better for text boxes and **Tolerance** mode for buttons

    5. set the :ref:`detection properties <visual_keywords-detection_settings>`;
    6. set the :ref:`interaction properties <visual_keywords-interaction_settings>`;
    7. click the *OK* button to save the keyword.


.. _visual_keywords-text_finder:

Text Finder
-----------

*Text Finders* produce Alyvix visual keywords that are able to **detect and interact with text** (e.g. button text, icon text). This is the *Text Finder* dialog:

    .. image:: pictures/ride_09_text_finder.png

To define such keywords follow these steps:

    1. select the Text Finder in the :ref:`selector of visual keywords <visual_keywords-keyword_definition>`;
    2. select :ref:`main and sub components <visual_keywords-text_definition>` of the selected Finder and press :kbd:`CTRL+O`;

    ..

        .. note::
            The Text Finder is designed to **primarly work in the ROI (region of interest) of the main component** as a fixed spot and not through out all the screen as the Image and Rect Finders. In fact, unlike the other Finders, you have also to select the ROI of the main component. So that, executing a Text Finder keyword alone, the text to match will be searched in the fixed ROI areas of its components. Thanks to the :ref:`Object Finders <visual_keywords-object_finder>` you can search text in a position that is related to other graphic elements (i.e. images, rectangles)

    3. type the :ref:`keyword name <visual_keywords-name_components>` and eventually set the number of arguments;
    4. the *Text Finder* features the properties to set the **regular expression** for matching the text (e.g. label, chunk) that you want to detect;

        * In the *Text* box you can insert a case insensitive **text string** (e.g. ``name``) as well as a **regular expression** (e.g. ``.*ame``). During the keyword execution, Alyvix will try to properly match that entry with the text within the ROI of the selected component;
        * In the *Text* box you can also use **arguments** passing text strings or regular expressions from the keyword arguments. :ref:`Add one or more arguements <visual_keywords-name_components>`, type ``arg1``, ``arg2``, etc. in the *Text* box and untick *Quotes*;
        * Click on the *Check* button to have a preview of what the OCR scanner will detect in the ROI of the selected component: *CRITICAL* means Alyvix is not able to match the regular expression you have provided, *EXCELLENT* instead means the text component can be found;

            ..

        ..

            .. note::
                As a general rule of thumb, try to **wrap uniform text with ROI** in order to obtain a **more accurate character recognition**. Sometimes though, you could suffer a poor character recognition (e.g. ``8`` instead of ``B``, ``1`` instead of ``t``): in these cases work on the regular expression to correct the detection

        * The characters from ROI pass through the *WhiteList* filter: the OCR scanner will limit the recognition to that set of characters. Moreover, the OCR scanner will interpret entire words from the language dictionary specified in the *Lang* box (type ``eng`` for English, ``ita`` for Italian and ``deu`` for German);

            .. image:: pictures/ride_09b_text_finder.png

    5. set the :ref:`detection properties <visual_keywords-detection_settings>`;
    6. set the :ref:`interaction properties <visual_keywords-interaction_settings>`;
    7. click the *OK* button to save the keyword.


.. _visual_keywords-object_finder:

Object Finder
-------------

The *Object Finder* is probably the most useful Alyvix Finder, because it **links together multiple types of Alyvix visual keywords** defining complex graphic objects to detect: a *Object Finder* considers its basic visual keywords as its main and sub components to search, inheriting their arguments as well. This is the *Object Finder* dialog:

    .. image:: pictures/ride_10_object_finder.png

To define such keywords follow these steps:

    1. define the :ref:`Image Finder <visual_keywords-image_finder>`, :ref:`Rect Finder <visual_keywords-rect_finder>` and :ref:`Text Finder <visual_keywords-text_finder>` keywords that will be components of the *Object Finder*;
    2. select the *Object Finder* in the :ref:`selector of visual keywords <visual_keywords-keyword_definition>`;
    3. type the :ref:`keyword name <visual_keywords-name_components>`;
    4. click on *Set Main* button to select the main component: a list of the defined Finders will appear from where choose an *Image Finder [IF]* or a *Rect Finder [RF]*;

        ..

    ..

        .. note::
            It is not possible to choose a *Text Finder [TF]* as the main component of an *Object Finder*, because it would not make sense: the *Text Finder* is designed to primarly search text in the fixed ROI (region of interest) area of its main component

    5. click on *Add Sub* button to select a sub component: a list of the defined Finders will appear from where choose an *Image Finders [IF]*, a *Rect Finders [RF]* and a *Text Finders [TF]*; you can add more sub components clicking on *Add Sub* every time;

        ..

    ..

        .. note::
            Select the main component and click on the *Edit* button to edit its definition; you can do the same for each sub component as well as redraw its ROI (*ROI Redraw* button) and remove it (*Remove* button)

            ..

                .. image:: pictures/ride_10b_object_finder.png

    6. set the :ref:`detection properties <visual_keywords-detection_settings>`;
    7. click the *OK* button to save the keyword.

You can build, for example, an *Object Finder* visual keyword made by an *IF* and a *TF* (with a regular expression as its argument). It is a powerful thing: you can use the same keyword several time to interact with different text elements in the same menu, just changing the *TF* regex argument.

Also an *Object Finder* made of a *RF* and a *TF* (with its argument) is useful: you can use *OF* visual keywords to interact with different rectangle buttons, identically shaped, but differently labeled.

    .. image:: pictures/ride_10bb_object_finder.png

..

    .. image:: pictures/ride_10cb_object_finder.png


.. _visual_keywords-alyvix_scrapers:

Alyvix Scrapers
===============


.. _visual_keywords-text_scraper:

Text Scraper
------------

*Text Scrapers* produce Alyvix visual keywords that are able to **scrap text** (e.g. window titles, text chunks). This is the *Text Scraper* dialog:

    .. image:: pictures/ride_09c_text_scraper.png

To define such keywords follow these steps:

    1. select the Text Finder in the :ref:`selector of visual keywords <visual_keywords-keyword_definition>`;
    2. select the :ref:`main component <visual_keywords-text_definition>` of the scraper (i.e. ROI and selection) and press :kbd:`CTRL+O`;
    3. type the :ref:`keyword name <visual_keywords-name_components>` and tick *Scraper*;
    4. the *Text Scraper* features the properties for scraping the text that you want to scrap;

        * Click on the *Check* button to have a preview of what the OCR scanner will scrap in the ROI of the main component;

            ..

        ..

            .. note::
                As a general rule of thumb, try to **wrap uniform text with ROI** in order to obtain a **more accurate character scraping**

        ..

        * The characters from ROI pass through the *WhiteList* filter: the OCR scanner will limit the scraping to that set of characters. Moreover, the OCR scanner will interpret entire words from the language dictionary specified in the *Lang* box (type ``eng`` for English, ``ita`` for Italian and ``deu`` for German);

            .. image:: pictures/ride_09d_text_scraper.png

    5. click the *OK* button to save the keyword.
