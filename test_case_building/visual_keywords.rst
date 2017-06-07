.. _visual_keywords:

***************
Visual keywords
***************


.. _visual_keywords-keyword_definition:

Keyword definition
==================

The :ref:`Alyvix button <testcase_editor-editor_buttons>` opens the **selector of visual keywords** (that has been previously defined by the user) for the current test case (e.g. ``alyvix_website``, so that its keyword library would be ``AlyvixProxyalyvix_website`` ``.py``). The selector lists the name and the type of each keyword: `[IF]` means Image Finder, `[RF]` means Rect Finder, `[TF]` means Text Finder and `[OF]` stays for Object Finder.

.. note::
    Imported keywords from other Alyvix test case libraries (e.g. ``citrix_outlook``, so that its keyword library would be ``AlyvixProxycitrix_outlook`` ``.py``) are not listed in the selector window. You can edit keywords of a certain test case just opening that test case.

..

    .. image:: pictures/ride_05a_keyword_selector.png

The *New* button opens the selector of the Alyvix Finders to define a new visual keyword. The *Edit* button brings to the Finder dialog of the selected keyword, in order to modify its properties (e.g. component and ROI selections, detection and interaction settings, performance thresholds). The *Remove* button deletes the selected keywords or in case of Object Finder keywords, crumbles them into its basic components (e.g. IF, RF, TF).

    .. image:: pictures/ride_05b_finder_selector.png

The Alyvix Finder selector allows selecting the type of a new keyword to define. The ``Delay`` spin control delays the subsequent selection of the main component to start defining a keyword of the selected type.

Start defining a custom keyword means visually selecting its components: one main selection is necessary, but then multiple sub selections are possible. The reasons for sub components are to detect application transactions in a more complete (GUI rendering could be element-by-element) and robust (the same GUI element could be used twice) way, besides being able to interact with more GUI elements (i.e. not just with the main component).

Each Alyvix Finder has its own procedure to select its components and ROI to bind subs to the main.


.. _visual_keywords-image_definition:

Image Finder main and subs
--------------------------

    .. image:: pictures/ride_07a_if_main_sub.png

An example GUI shows three identical stars, but a possible transaction could be interacting with the third, left to the green sign. Selecting just the star, as a main component, is not enough: Alyvix is going to detect all the three stars and to interact with the first one, because of a raster logic scanning the screen.
To correctly define the keyword, it is necessary to also select the green sign as a sub component. Sub components of Image Finders lies in their ROI. The upper left corner of ROI are all binded with the upper left corner of the main component selection.

    .. image:: pictures/ride_07bb_if_main_sub.png

..

    1. Selection of main component inside the screen
    2. Selection of the ROI of the sub component 1 inside the screen
    3. Selection of the sub component 1 inside its ROI
    4. Eventual repetition of 2. and 3. to add more and more sub components
    5. Press CTRL + O to access the setting dialog of the Image Finder


.. _visual_keywords-rect_definition:

Rect Finder main and subs
-------------------------

    .. image:: pictures/ride_07c_rf_main_sub.png

An example GUI shows three identical edit boxes, but a possible transaction could be interacting with the third, left to the ‘OK’ button. Selecting just the edit box, as a main component, is not enough: Alyvix is going to detect all the three edit boxes and to interact with the first one, because of a raster logic scanning the screen.
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

All the dialogs of Alyvix Finders have in common most of their settings. Right after the component selection of an Alyvix Finder, the  CTRL  +  O  shortcut opens the setting dialog of the Finder where to finalize the definition of an Alyvix custom keyword.

The ‘Graphic Design’ tab is the richest of settings. First of all, type the custom keyword name. The best practice is to type a lowercase name, with underscores, no spaces and a structure as the following: <testcase sub section name>_<transaction name>_<finder type> (e.g.mywebsite_homepage_img).

In the left pane there are all the components previously selected: tick or untick them to visualize their selection and ROI on screen or not. Click on each component to set its name, its detection and interaction options.

Three are the detection modes. ‘Wait’ means Alyvix continuously tries and retries to detect the graphic elements on screen at a certain pace (by default this period is 2.5s, but it is customizable thanks to the basic keywords Alyvix Config and Set Alyvix Info). That continues until the ‘Timeout’ threshold will be reached: if the ‘Exception’ option is ticked, then the keyword breaks the test case, otherwise it returns False and lets the test to proceed. The latter option is useful in case of transactions that not always happen (e.g. to manage popups). ‘Wait Disappear’ allows to detect the disappearance of graphic elements of screen (e.g. disappearance of an hourglass icon at the end of a loading).

The available interaction options are self-explained. ‘Click’, ‘Right Click’ and ‘Double Click’ means Alyvix will bring instantly the mouse pointer over the detected component and interact with it pressing, respectively, one time the left button of the mouse, one time the right button of the mouse and two times the left button of the mouse. ‘Move’ will bring instantly the mouse pointer over the detected component without sending any keystroke. ‘Don’t Move’ will do nothing with a component after its detection.

At the bottom of the ‘Graphic Design’ window, typing settings take place. Within the edit box can be inserted text strings and shortcuts to send (most of the time after a ‘Click’ interaction somewhere). Regular text strings can be typed together with shortcuts (e.g. bla{enter}). You can find a list of the most useful shortcuts in the description of  Send Keys basic keyword. However, it is also possible to bring the keyword arguments as part of the keystrokes to send. In this latter case, it is necessary to untick ‘Add Quotes’, then to add one more argument under the ‘Source Code’ tab (click up at the ‘Args’ spin box) and finally use the argument variable alone (e.g. arg1) or properly formatted with the rest, as following example: “bla{enter}”+arg1+”{enter}”.

Finally, the ‘Performance Data’ tab shows the performance settings. First, the ‘Enable Performance’ check box to enable or to disable the performance measurement: for example, in case of automation transactions, that are defined to reach the interesting parts of user flows, we do not care about performances. Second, in the two edit boxes we can set the amount of seconds of Warning and Critical thresholds.


.. _visual_keywords-image_finder:

Image Finder
------------

Image Finders are featured by a spin box where to set the likelihood threshold for the selected component. You have to set a number between 0 and 1, with two decimal places: higher that threshold is, more similar a graphic element on screen has to be respect to the selected component.

    .. image:: pictures/ride_06a_image_finder.png

..

    .. image:: pictures/alyvix_image_finder.gif


.. _visual_keywords-rect_finder:

Rect Finder
-----------

There are two modes in order to define valid rectangles: Min/Max and Tolerance boundaries. Click on one of them and tick its check box on the right to see the ongoing editing of valid areas. Type integer numbers, click spin boxes or scroll mouse wheel to change the violet area on selected components: rectangle contours on screen (or in ROI for sub components) that fit the adjusted boundaries will be take into account by Alyvix.

    .. image:: pictures/ride_08_rect_finder.png


.. _visual_keywords-text_finder:

Text Finder
-----------

In the ‘Text’ edit box of Text Finders you can provide a case insensitive text string (e.g. name) as well as a regular expression (e.g. .*ame). Both of them are going to be match with the text into the selected component ROI. The characters from ROI pass through the ‘WhiteList’ filter: just from that set, the OCR scanner will choose the characters to match with the provided text string. Click on ‘Check’ button to have a preview of what the OCR scanner will detect in the ROI: ‘CRITICAL’ means Alyvix is not able to match the regular expression you have provided, ‘EXCELLENT’ instead means the text component can be found.

In the ‘Text’ edit box can be also used arguments. If you want to pass a text string or a regular expression to a Text Finder custom keyword as its argument, type arg<n> (e.g. arg1) in the edit box, untick ‘Add Quotes’, add one more ‘Args’ under the ‘Source Code’ tab and finally remember to pass a text to match as the keyword argument (e.g. mywebsite_userlist_txt | .*ame).

    .. image:: pictures/ride_09_text_finder.png


.. _visual_keywords-object_finder:

Object Finder
-------------

Object Finders are the most useful Alyvix Finder, because they bind together multiple types of Alyvix custom keywords, taking also into account automatically all their arguments. That means you can build, for example, an Object Finder custom keyword made by an IF and a TF with its argument. It is a powerful thing: you can use the same keyword several time to interact with different elements in the same menu. Also an OF made by a RF and a TF with its argument is useful: you can use Object Finder custom keywords to interact with different buttons identically shaped, but differently titled.

First, you have to build IF, RT and TF custom keywords to make an OF. Second, create an OF and set its main and sub components pressing the ‘Set Main Object’ and ‘Add Sub Object’ button. Finally, redefine the ROI to bind the added sub component to the main one drawing a searching area around the sub component selection.

The ‘Edit’ and ‘Remove’ buttons allow to edit the settings of the selected component or to delete it from the OF component list on the left pane: if you remove the main from an OF, you have to set a new one.

    .. image:: pictures/ride_10_object_finder.png

..

    .. image:: pictures/ride_10bb_object_finder.png

..

    .. image:: pictures/ride_10cb_object_finder.png
