# Titanium Module for Google Cloud Messaging Push Notifications for Android #

A Titanium module for registering a device with GCM and handling push notifications sent to the device.

1. Install the module as usual in Titanium Studio by downloading the [zip file](https://github.com/morinel/gcmpush/releases/download/1.0/nl.vanvianen.android.gcm-android-1.0.zip)
1. Refer to the example for possibilities
1. Send a server push notification with your preferred server-side technology to the registrationId returned while registering your device.
1. The callback you specified will then be called

This module does not require any tiapp.xml properties, all configuration is done in Javascript.

There are four notification settings that can be specified:

1. sound: the sound file to play while receiving the notification or 'default' for the default sound. The sound file should be placed in platform/android/res/raw directory.
1. smallIcon: the tiny icon shown at the top of the screen, see this [stackoverflow question](http://stackoverflow.com/questions/28387602/notification-bar-icon-turns-white-in-android-5-lollipop) for details. The file should be placed in platform/android/res/drawable 
1. largeIcon: the large icon shown in the notification bar. If not specified your appicon will be used. The file should be placed in platform/android/res/drawable.
1. vibrate (true / false): whether vibration should be on 


If the app is not active when the notification is received, use gcm.getLastData() to retrieve the contents of the notification and act accordingly to start or resume the app in a suitable way. If you're done, call gcm.clearLastData(), otherwise the same logic will happen when resuming the app again.
