*********************************
Graphic detection and interaction
*********************************


One transaction, one Alyvix custom keyword, one performance
===========================================================

Alyvix provides tools to define any application transaction. Defining **one transaction** means building one so-called **Alyvix custom keyword**, so that Alyvix users have to select graphic elements on the screen and to specify the modes to interact with them. Executing a custom keyword Alyvix starts a process aimed to detect the defined graphics and then to interact with them.

The Alyvix performance measurement system guarantees the output performance time of a transaction is net, so it is provided without taking into account the processing time of detection and interaction. Alyvix can provide **one performance** for each executed transaction.

Executing a test case means executing a sequence of keywords including Alyvix custom keywords. Each of them defines a transaction and outputs a performance. The latter are strictly calculated from the start of keyword executions to the time when the graphic elements they defined appear on screen. For a custom keyword within a test case, that means from the end of the previous keyword execution to the appearance of the current one.


Alyvix custom keywords: types, components, regions of interest
==============================================================

Alyvix custom keywords can detect any type or amount of graphic element on a computer screen and interact with them in any modes (e.g. mouse clicks, keystrokes). It is possible to build several types of keywords to work with several types of graphics: **images**, **rectangles**, **text strings**.

The **Alyvix Finders** are GUI tools working on screen that allow you to select an ordered sequence of one main and multiple sub components for every Alyvix custom keyword that you build. Keywords exit successfully if and only if Alyvix properly detects all their defined and listed graphic elements. Right after a successful detection step Alyvix can interact with components as defined, so if some component is missing there cannot be any interaction phase.

The reasons for **multiple components** in keywords are the following: mainly, it is necessary to disambiguate groups of elements partly identical and secondly, that also allows to interact separately and in different ways with each component. The multiple component selection strengthens test cases, because users are able to define **unambiguous transactions**.

Users have also to draw the so-called rectangular **regions of interest** (ROI) for every custom keyword with multiple components. ROI bind the main component of a keyword with its sub components. Alyvix looks for the main component within the entire screen, but it looks for sub components just within their own regions of interest.

Regions of interest allow **flexibility** to transactions: no matter if some sub components will be rendered in a different position on screen, if they lie into their ROI Alyvix will be able to detect them.


Alyvix Object Finder: multitype components
==========================================

Besides the basic Alyvix tools (i.e. Image Finder, Rect Finder, Text Finder) it also provides the **Object Finder** which is a **multitype container** of basic Alyvix Finders.

The logic behind Object Finders is the same as basic ones (several components with their regions of interest), the difference is that Object Finder components are basic Alyvix Finders of several types. For example, as main component could be an Image Finder, as first sub component could be a Rect Finder and as second sub component could be a Text Finder. Each sub component binds to the main one through ROI.

Text Finders can take the text string to search as an argument. That means a useful Object Finder is made of an Image Finder as the main component and a Text Finder as a sub component. In this case, users can recall the **same keyword** with **different arguments** in order to interact with different elements that are identical on the image side but different on the text side. That is exactly the case of element in a tree view: every element in the list has the same arrow icon on the left and different text descriptions on the right.


Interaction modes: mouse clicks and keystrokes
==============================================

Users have to define one **interaction mode** for every component (i.e. main and sub ones) in every Alyvix custom keyword they build. Alyvix can interact with GUI elements in the following ways: doing nothing, **moving** over the component, left/right/double **clicking** on the component and **typing** text strings, keyboard shortcuts or a mix of them.

**Text strings** or **keyboard shortcuts** can be passed to keywords as arguments: users can reuse the same keyword multiple times within a test case, but each time interacting with different keystrokes. Furthermore, it is sometimes faster just to push keybindings to an application instead of browsing its GUI to complete user transactions that are not critical (e.g. browsing application menus, closing application windows).
