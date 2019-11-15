Get Started with Remote Debugging Android Devices
=================================================
.. https://developers.google.com/web/tools/chrome-devtools/remote-debugging?utm_campaign=2016q3&utm_medium=redirect&utm_source=dcc


Remote debug live content on an Android device from your Windows, Mac, or Linux computer. This tutorial teaches you how to:

- Set up your Android device for remote debugging, and discover it from your development machine.
- Inspect and debug live content on your Android device from your development machine.
- Screencast content from your Android device onto a DevTools instance on your development machine.

.. image :: img/remote-debugging.png

**Figure 1**. Remote Debugging lets you inspect a page running on an Android device from your development machine.

Step 1: Discover your Android device
------------------------------------

The workflow below works for most users. See Troubleshooting: DevTools is not detecting the Android device for more help.

1. Open the ``Developer Options`` screen on your Android. See Configure On-Device Developer Options.
2. Select ``Enable USB Debugging``.
3. On your development machine, open Chrome.
4. Open DevTools.
5. In DevTools, click the ``Main Menu`` then select ``More tools > Remote devices``

.. image :: img/open-remote-devices.png

**Figure 2**. Opening the ``Remote Devices`` tab via the ``Main Menu``

6. In DevTools, open the Settings tab.
7. Make sure that the Discover USB devices checkbox is enabled.

.. image :: img/discover-usb-devices.png

**Figure 3**. The Discover USB Devices checkbox is enabled

8. Connect your Android device directly to your development machine using a USB cable. The first time you do this, you usually see that DevTools has detected an unknown device. If you see a green dot and the text Connected below the model name of your Android device, then DevTools has successfully established the connection to your device. Continue to Step 2.

.. image :: img/unknown-device.png

**Figure 4**. The ``Remote Devices`` tab has successfully detected an unknown device that is pending authorization

9. If your device is showing up as ``Unknown``, accept the ``Allow USB Debugging`` permission prompt on your Android device.

Troubleshooting: DevTools is not detecting the Android device
.............................................................

Step 2: Debug content on your Android device from your development machine
--------------------------------------------------------------------------

1. Open Chrome on your Android device.
2. In the Remote Devices tab, click the tab that matches your Android device model name. At the top of this page, you see your Android device's model name, followed by its serial number. Below that, you can see the version of Chrome that's running on the device, with the version number in parentheses. Each open Chrome tab gets its own section. You can interact with that tab from this section. If there are any apps using WebView, you see a section for each of those apps, too. In Figure 5 there are no tabs or WebViews open.

.. image :: img/connected-remote-device.png

**Figure 5**. A connected remote device

3. In the New tab text box, enter a URL and then click Open. The page opens in a new tab on your Android device.
4. Click Inspect next to the URL that you just opened. A new DevTools instance opens. The version of Chrome running on your Android device determines the version of DevTools that opens on your development machine. So, if your Android device is running a very old version of Chrome, the DevTools instance may look very different than what you're used to.
















