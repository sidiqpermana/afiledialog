# Overview #

**aFileDialog** is an Android library which implements a simple and easy to use _**file chooser**_.

His main features are:
  * The file chooser can be opened both as a _Dialog_ or as an _Activity_.
  * You can filter the files using regular expressions.
  * Can select files or folders.
  * Can create files and folders.

_aFileDialog_ is open source, licensed under LGPL 3, and is compatible with Android 2.2+.

[Download it here](http://afiledialog.googlecode.com/svn/aFileDialog-1.04-Full.zip) or visit the [Downloads](Downloads.md) section.

You can also install the showcase app, available at [Google Play](https://play.google.com/store/apps/details?id=ar.com.daidalos.afiledialog.test).

| ![http://afiledialog.googlecode.com/svn/wiki/screenshot2.png](http://afiledialog.googlecode.com/svn/wiki/screenshot2.png) | ![http://afiledialog.googlecode.com/svn/wiki/screenshot3.png](http://afiledialog.googlecode.com/svn/wiki/screenshot3.png) | ![http://afiledialog.googlecode.com/svn/wiki/screenshot4.png](http://afiledialog.googlecode.com/svn/wiki/screenshot4.png) | ![http://afiledialog.googlecode.com/svn/wiki/screenshot5.png](http://afiledialog.googlecode.com/svn/wiki/screenshot5.png) |
|:--------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------|

# How to use it #

In order to use _aFileDialog_ in your application you must do three steps:

**1)** Add a reference to the library project. Note that, since _aFileDialog_ is a _Android Library project_, it can not be compiled into a binary file (such as a JAR file), so your project must reference to the _aFileDialog_ project, instead of reference to a single JAR file.

**2)** Declare the activity _FileChooserActivity_ in the _manifest_ file. This can be done by adding the following lines inside the tags `</application>\</application>`:

```xml

<activity android:name="ar.com.daidalos.afiledialog.FileChooserActivity" />```

**3)** Add the permission _READ\_EXTERNAL\_STORAGE_ to the _manifest_ file, if you want to access the SD card (and if you are using Android 4.1 or superior).

```xml

<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />```

Then you must only create an instance of _FileChooserDialog_ and call the _show()_ method or start the activity _FileChooserActivity_.

# Documentation #

_aFileDialog_ has been designed in order to be easy to use and easy to develop.

In order to known how to use _aFileDialog_, check the [user guide](UserGuide.md) (also available in [Spanish](UserGuideEs.md) and [French](UserGuideFr.md)).

If you want to modify or extend _aFileDialog_, you can read the [software design description](SoftwareDesignDescription.md) (also available in [Spanish](SoftwareDesignDescriptionEs.md)), although this is not mandatory, since the code is fully commented and you are going to figure out how it works in matters of minutes.

# Examples #

Samples codes are available in the [user guide](UserGuide.md), but, to summarize, you can open a file chooser (implemented with a _Dialog_) using the following lines:

```java

FileChooserDialog dialog = new FileChooserDialog(context);
dialog.show();```

To open a file chooser implemented with an _Activity_, you can use the following lines:

```java

Intent intent = new Intent(this, FileChooserActivity.class);
this.startActivityForResult(intent, 0);```