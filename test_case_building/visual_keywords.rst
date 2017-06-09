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

You can declare a number of **argument variables as the keyword inputs**. You can then type ``arg1``, ``arg2``, etc. in the :ref:`interaction text box <visual_keywords-interaction_settings>` below. Alyvix will run the keyword taking its **arguments from the test case editor**: in the cells right from where you insert the keyword name, you can type its **arguments as text strings**.

    .. image:: pictures/ride_11a_alyvix_2-4-1_gui_name.png

In the left pane of the dialog there are all the **components** previously selected on screen: tick (or untick) them to visualize (or not) their selection and ROI on screen. Click on each component to set its own detection and interaction properties.

    .. image:: pictures/ride_11b_alyvix_2-4-1_gui_components.png


.. _visual_keywords-detection_settings:

Detection settings
------------------

Three are the detection modes. ‘Wait’ means Alyvix continuously tries and retries to detect the graphic elements on screen at a certain pace (by default this period is 2.5s, but it is customizable thanks to the basic keywords Alyvix Config and Set Alyvix Info). That continues until the ‘Timeout’ threshold will be reached: if the ‘Exception’ option is ticked, then the keyword breaks the test case, otherwise it returns False and lets the test to proceed. The latter option is useful in case of transactions that not always happen (e.g. to manage popups). ‘Wait Disappear’ allows to detect the disappearance of graphic elements of screen (e.g. disappearance of an hourglass icon at the end of a loading).

Finally, the ‘Performance Data’ tab shows the performance settings. First, the ‘Enable Performance’ check box to enable or to disable the performance measurement: for example, in case of automation transactions, that are defined to reach the interesting parts of user flows, we do not care about performances. Second, in the two text boxes we can set the amount of seconds of Warning and Critical thresholds.

    .. image:: pictures/ride_11c_alyvix_2-4-1_gui_detection.png


.. _visual_keywords-interaction_settings:

Interaction settings
--------------------

The available interaction options are self-explained. ‘Click’, ‘Right Click’ and ‘Double Click’ means Alyvix will bring instantly the mouse pointer over the detected component and interact with it pressing, respectively, one time the left button of the mouse, one time the right button of the mouse and two times the left button of the mouse. ‘Move’ will bring instantly the mouse pointer over the detected component without sending any keystroke. ‘Don’t Move’ will do nothing with a component after its detection.

At the bottom of the ‘Graphic Design’ window, typing settings take place. Within the text box can be inserted text strings and shortcuts to send (most of the time after a ‘Click’ interaction somewhere). Regular text strings can be typed together with shortcuts (e.g. bla{enter}). You can find a list of the most useful shortcuts in the description of  Send Keys basic keyword. However, it is also possible to bring the keyword arguments as part of the keystrokes to send. In this latter case, it is necessary to untick ‘Add Quotes’, then to add one more argument under the ‘Source Code’ tab (click up at the ‘Args’ spin box) and finally use the argument variable alone (e.g. arg1) or properly formatted with the rest, as following example: “bla{enter}”+arg1+”{enter}”.

    .. image:: pictures/ride_11d_alyvix_2-4-1_gui_interaction.png


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

In the ‘Text’ text box of Text Finders you can provide a case insensitive text string (e.g. name) as well as a regular expression (e.g. .*ame). Both of them are going to be match with the text into the selected component ROI. The characters from ROI pass through the ‘WhiteList’ filter: just from that set, the OCR scanner will choose the characters to match with the provided text string. Click on ‘Check’ button to have a preview of what the OCR scanner will detect in the ROI: ‘CRITICAL’ means Alyvix is not able to match the regular expression you have provided, ‘EXCELLENT’ instead means the text component can be found.

In the ‘Text’ text box can be also used arguments. If you want to pass a text string or a regular expression to a Text Finder custom keyword as its argument, type arg<n> (e.g. arg1) in the text box, untick ‘Add Quotes’, add one more ‘Args’ under the ‘Source Code’ tab and finally remember to pass a text to match as the keyword argument (e.g. mywebsite_userlist_txt | .*ame).

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
