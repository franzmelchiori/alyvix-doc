.. _visual_keywords:

***************
Visual keywords
***************


.. _visual_keywords-keyword_definition:

Keyword definition
==================

The :ref:`Alyvix button <testcase_editor-editor_buttons>` opens the **selector of visual keywords** (that has been previously defined by the user) for the current test case (e.g. ``alyvix_website``, so that its keyword library would be ``AlyvixProxyalyvix_website`` ``.py``). The selector shows the name and the type of each keyword: *[IF]* means :ref:`Image Finder <visual_keywords-image_finder>`, *[RF]* means :ref:`Rect Finder <visual_keywords-rect_finder>`, *[TF]* means :ref:`Text Finder <visual_keywords-text_finder>` and *[OF]* stays for :ref:`Object Finder <visual_keywords-object_finder>`.

.. note::
    *Imported keywords* from other *Alyvix test case libraries* (e.g. ``citrix_outlook``, so that its keyword library would be ``AlyvixProxycitrix_outlook`` ``.py``) are *not* listed in the selector window. You can edit keywords in a certain test case library just opening that test case.

..

    .. image:: pictures/ride_05a_keyword_selector.png

The *New* button opens the selector of :ref:`Alyvix Finders <visual_keywords-alyvix_finders>`. The *Edit* button brings to the Finder dialog of the selected keyword, in order to modify its properties (e.g. component and ROI selections, detection and interaction settings, performance thresholds). The *Remove* button deletes the selected keywords or, in case of :ref:`Object Finder <visual_keywords-object_finder>` keywords, crumbles them into its basic components (IF, RF, TF).

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

Selecting just the third star, as a main component of an *Image Finder*, is not enough. It would be an ambiguous transaction: the three stars have exactly the same aspect. Alyvix detects all the three stars and then interacts with the first one, because of the raster logic of screen scanner.

To correctly define the keyword, it is necessary to **select the green sign as a sub component**. Remember that sub components of Image Finders are selected within their ROI. The upper left corner of ROI are linked with the upper left corner of the main component selection.

    .. image:: pictures/ride_07bb_if_main_sub.png

..

    1. Select the **main component** inside the screen;
    2. select the **ROI** of the sub component 1 inside the screen;
    3. select the **sub component** 1 inside its ROI;
    4. eventually repeat 2. and 3. to add more sub components;
    5. press :kbd:`CTRL+O` to set the :ref:`IF keyword properties <visual_keywords-image_finder>`.


.. _visual_keywords-rect_definition:

Rect Finder main and subs
-------------------------

    .. image:: pictures/ride_07c_rf_main_sub.png

An example GUI shows three identical text boxes, but a possible transaction could be interacting with the third, left to the ‘OK’ button. Selecting just the text box, as a main component, is not enough: Alyvix is going to detect all the three text boxes and to interact with the first one, because of a raster logic scanning the screen.
To correctly define the keyword, it is necessary to also select the ‘OK’ button as a sub component. Sub components of Rect Finders lies in their ROI. The upper left corner of ROI are all binded with the upper left corner of the main component selection.

    .. image:: pictures/ride_07db_rf_main_sub.png

..

    1. Selection of main component inside the screen
    2. Selection of the ROI of the sub component 1 inside the screen
    3. Selection of the sub component 1 inside its ROI
    4. Eventual repetition of 2. and 3. to add more and more sub components
    5. Press CTRL + O to access the setting dialog of the Rect Finder


.. _visual_keywords-text_definition:

Text Finder main and subs
-------------------------

    .. image:: pictures/ride_07e_tf_main_sub.png

An example GUI shows three identical ‘Name’ text strings, but a possible transaction could be interacting with the third, left to the ‘Franz’ text string. Selecting just the ‘Name’ text string, as a main component, is not enough: Alyvix is going to detect all the three ‘Name’ text strings and to interact with the first one, because of a raster logic scanning the screen.
To correctly define the keyword, it is necessary to also select the ‘Franz’ text string as a sub component. All Text Finder components (main and sub) lies in their ROI. The upper left corner of ROI are all binded with the upper left corner of the screen. That differs from the Image and Rect Finders: the main component of Text Finder is searched within its ROI and not on the entire screen. The latter is the reason why Text Finder should be strictly used as sub components of Object Finders.

    .. image:: pictures/ride_07fb_tf_main_sub.png

..

    1. Selection of the ROI of the main component inside the screen
    2. Selection of main component inside its ROI
    3. Selection of the ROI of the sub component 1 inside the screen
    4. Selection of the sub component 1 inside its ROI
    5. Eventual repetition of 3. and 4. to add more and more sub components
    6. Press CTRL + O to access the setting dialog of the Text Finder


.. _visual_keywords-object_definition:

Object Finder main and subs
---------------------------

    .. image:: pictures/ride_07g_of_main_sub.png

An example GUI shows three identical stars, but a possible transaction could be interacting with the third, left to the ‘Franz’ text string. Selecting just the star, as a main component, is not enough: Alyvix is going to detect all the three stars and to interact with the first one, because of a raster logic scanning the screen.
To correctly define the keyword, it is necessary to also select the ‘Franz’ text string as a sub component. Firstly, define an Image Finder with the star and a Text Finder with the ‘Franz’ text string. Secondly, select them as the main and a sub component of an Object Finder. Finally, redefine the ROI of sub components to bind them to the main component.
The most common and useful Object Finder combinations are IF + TF and RF + TF.

    .. image:: pictures/ride_07hb_of_main_sub.png

..

    1. Selection of the main component
    2. Selection of the sub component 1
    3. Selection of the ROI of the sub component 1
    4. Eventual repetition of 2. and 3. to add more and more sub components
    5. Press CTRL + O to access the setting dialog of the Object Finder


.. _visual_keywords-alyvix_finders:

Alyvix Finders
==============

The *Alyvix Finders* are the GUI tools to **visually define application transactions**. You can build *Alyvix visual keywords* with the Alyvix Finders. Finally, you can automate application transactions running Alyvix visual keywords in test cases. There are three Alyvix Finders, one for each **type of visual element to detect** on screen: images, rectangles and text. The *Object Finder* group together basic Alyvix Finders (IF, RF, TF) in order to detect and interact with **different types of visual elements** running one single keyword (e.g. a login form made of text boxes, their labels on a side and a brand logo in a corner).

After the :ref:`selection of an Alyvix Finder <visual_keywords-keyword_definition>` and the :ref:`selection of main and sub components <visual_keywords-image_definition>`, press :kbd:`CTRL+O` to **show the setting dialog**. The Image, Rect and Text Finders have in common most of their settings:

* :ref:`Name and components <visual_keywords-name_components>`
* :ref:`Detection settings <visual_keywords-detection_settings>`
* :ref:`Interaction settings <visual_keywords-interaction_settings>`

The :ref:`Image Finder <visual_keywords-image_finder>` has its own similarity threshold, the :ref:`Rect Finder <visual_keywords-rect_finder>` has sizing thresholds and the :ref:`Text Finder <visual_keywords-text_finder>` has regular expression filters. The :ref:`Object Finder <visual_keywords-object_finder>` dialog is designed to link together the previous basic Alyvix Finders.


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

In the left pane of the dialog there are all the **components** previously selected on screen: tick (or untick) them to visualize (or not) their *selection* and *ROI* on screen. Click on each component to set its own detection and interaction properties.

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

    .. image:: pictures/ride_11d_alyvix_2-4-1_gui_interaction.png

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
            To drag'n'drop a GUI element (look at the example above) it is necessary to set the *Hold* mode for **a target component** (e.g. file icon) and the *Release* mode for **another destination component** (e.g. folder icon).

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


.. _visual_keywords-image_finder:

Image Finder
------------

*Image Finders* produce Alyvix visual keywords that are able to detect and interact with **images** (i.e. pixel matrixes). This is the *Image Finder* dialog:

    .. image:: pictures/ride_06a_image_finder.png

To define such keywords follow these steps:

    1. select the :ref:`Image Finder <visual_keywords-keyword_definition>`;
    2. select :ref:`main and sub components <visual_keywords-image_definition>`;
    3. type the :ref:`keyword name <visual_keywords-name_components>` and eventually set the number of arguments;
    4. *Image Finders* are featured by a spin box where to set the **visual likelihood threshold** for the selected component. You can set a number between 0 and 1, with two decimal places. The default value is ``0.70`` and it works just fine most of the cases;

        .. image:: pictures/ride_06ab_image_finder.png

    ..

        .. note::
            To **disambiguate graphical elements** in a transaction, it is better to **add more components** instead of increasing the visual likelihood threshold.

    5. set the :ref:`detection properties <visual_keywords-detection_settings>`;
    6. set the :ref:`interaction properties <visual_keywords-interaction_settings>`.


.. _visual_keywords-rect_finder:

Rect Finder
-----------

    .. image:: pictures/ride_08_rect_finder.png

There are two modes in order to define valid rectangles: Min/Max and Tolerance boundaries. Click on one of them and tick its check box on the right to see the ongoing editing of valid areas. Type integer numbers, click spin boxes or scroll mouse wheel to change the violet area on selected components: rectangle contours on screen (or in ROI for sub components) that fit the adjusted boundaries will be take into account by Alyvix.

    .. image:: pictures/ride_08b_rect_finder.png


.. _visual_keywords-text_finder:

Text Finder
-----------

    .. image:: pictures/ride_09_text_finder.png

In the ‘Text’ text box of Text Finders you can provide a case insensitive text string (e.g. name) as well as a regular expression (e.g. .*ame). Both of them are going to be match with the text into the selected component ROI. The characters from ROI pass through the ‘WhiteList’ filter: just from that set, the OCR scanner will choose the characters to match with the provided text string. Click on ‘Check’ button to have a preview of what the OCR scanner will detect in the ROI: ‘CRITICAL’ means Alyvix is not able to match the regular expression you have provided, ‘EXCELLENT’ instead means the text component can be found.

In the ‘Text’ text box can be also used arguments. If you want to pass a text string or a regular expression to a Text Finder custom keyword as its argument, type arg<n> (e.g. arg1) in the text box, untick ‘Add Quotes’, add one more ‘Args’ under the ‘Source Code’ tab and finally remember to pass a text to match as the keyword argument (e.g. mywebsite_userlist_txt | .*ame).

    .. image:: pictures/ride_09b_text_finder.png


.. _visual_keywords-object_finder:

Object Finder
-------------

    .. image:: pictures/ride_10_object_finder.png

Object Finders are the most useful Alyvix Finder, because they bind together multiple types of Alyvix custom keywords, taking also into account automatically all their arguments. That means you can build, for example, an Object Finder custom keyword made by an IF and a TF with its argument. It is a powerful thing: you can use the same keyword several time to interact with different elements in the same menu. Also an OF made by a RF and a TF with its argument is useful: you can use Object Finder custom keywords to interact with different buttons identically shaped, but differently titled.

First, you have to build IF, RT and TF custom keywords to make an OF. Second, create an OF and set its main and sub components pressing the ‘Set Main Object’ and ‘Add Sub Object’ button. Finally, redefine the ROI to bind the added sub component to the main one drawing a searching area around the sub component selection.

The ‘Edit’ and ‘Remove’ buttons allow to edit the settings of the selected component or to delete it from the OF component list on the left pane: if you remove the main from an OF, you have to set a new one.

    .. image:: pictures/ride_10bb_object_finder.png

..

    .. image:: pictures/ride_10cb_object_finder.png
