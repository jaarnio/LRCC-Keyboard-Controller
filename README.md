# LRCC-Keyboard-Controller
X-Keys ControllerMate control for Adobe Lightroom CC

Requirements:
MacOS High Sierra (Mojave possible, untested)
ControllerMate 4.11 or later (https://www.orderedbytes.com/controllermate/)
Adobe Lightroom CC (v8+) 
  Please note that with future releases of Lightroom, the ControllerMate layout may need updating.
XKeys XK60 60-key USB keyboard (https://xkeys.com/xk60.html)

Shuttle Contour Pro USB jog dial (optional)


Installation:
(1) Install ControllerMate Software
(2) Import the CMATE layout file and make active
(3) Give Accessibility permission to the ControllerMate application:
    System Preferences -> Security and Privacy -> Accessibility
    ControllerMate and ControllerMate Helper
(4) Copy the LR_dev_window_index.plist file to "/Library/Application Support/ControllerMate/".  This is the same folder the ControllerMateHelper app is located.
(5) Run Lightroom and test

How Does This Work:
This uses a combination of standard keypresses that are available in Lightroom, plus embedded AppleScript UI Accessibility controls for manipulating sliders in the Develop Module. The "Module Check" node under the "General" tab contains a very important logic structure that keeps track of the UI Acessibility Window data in the Lightroom CC application. This writes a PLIST file to the ControllerMate Helper app directory. This routine ensures that when Lightroom is the active application, ControllerMate has the correct window ID data in order to address the individual sliders.

*** You MUST take the time to learn the ControllerMate application before diving in to make modifications to the layout files. This configuration has been used in a production setting for many years, and there are generally good reasons why things are configured the way they are.

Troubleshooting:
If the keyboard won't link to Lightroom and control anything, it is likely due to the fact that the system NAME of the application Lightroom has changed.

The first thing to check is the root node that activates the ControllerMate module. Navigate to "General -> Module Check".  Check the properties of the "Lightroom" building block and ensure it matches the name of the application correctly.

The second thing to check is the Applescript routines that are bound to the Develop Module keys. These use standard Mac UI Accessbility formatting, so check that the NAME of the Lightroom application is set correctly.
