SCW-Skins
=========

Skins for Simple Calendar Widget

## Developer Guide

* Introduction
* Environement setup
* Testing/Running
* Skin creation
* Compatibility


### Introduction

Skin is an Android appliction that contain layout, graphics and configuration definitions.
This format allows to create unique flexible layouts (in contrast to other formats: custom images )
and apply properties to the layout that are not available from the widget code
(shadows, rounded corners, custom margins)

### Environement setup

In order to create skin you need to have installed:
  * Java JDK - http://www.oracle.com/technetwork/java/javase/downloads/index.html
  * Android SDK - http://developer.android.com/sdk/index.html
  * Eclipse - http://www.eclipse.org/downloads/
  * ADT Plugin for Eclipse - http://developer.android.com/sdk/eclipse-adt.html
  * USB Drivers for phone

Detailed instruction available here: http://developer.android.com/sdk/installing.html

#### Test usb drivers
* After downloading installing Android SDK you will have 'adb' tool inside <path-to-sdk>/platform-tools folder
* Open command-line and navigate to the place with adb
* run 'adb devices' command
* if device driver is installed you will see similar output

		alex@alex-P55M-UD2:~/android-sdk-linux/platform-tools$ adb devices 
		List of devices attached 
		0146914B1500D01A  device 

#### Test installation
After finish setup you can download a skin and try to run it on your device:
  * Download and extract examples - https://github.com/anod/SCW-Skins/download
  * Open Eclise, Navigate to File -> Import... -> Existing Projects into Workspace
  * In the Import dialog point root directory to the folder with exptracted skins sources
  * Select projects that you whant to import and click Finish
  * The projects will appear in Package Explorer
  * Select a project with skin, right click on it and choose from menu Run As -> Android Application 
  * If everything is fine you will see 'Installaion Complete.' message in the Console output

### Skin creation

#### Basic structure of files

    AndroidManifest.xml - Manifest file must include skin identification flag
    res/ 
        layout/skin.xml              - main layout
        layout/skin_row.xml          - layout of row of event
        layout/skin_row_noevents.xml - layout of row without events
        drawable/preview.png         - preview image of skin
        drawable/ic_launcher.png     - icon
        values/settings.xml          - skin settings
        values/strings.xml           - skin texts
   
More information about folder structure: http://developer.android.com/guide/topics/resources/providing-resources.html

#### Main layout
Main container of skin

Location: /res/layout/skin.xml

Predefined views

    View         :: @+id/container - Background of the wiget
    View         :: @+id/btn_datebox - Click on the view will open calendar in month view
    TextView     :: @+id/weekday - day of week
    TextView     :: @+id/daynum - todays day of month
    LinearLayout :: @+id/events_list - event row will be attached to it (for Android 3.0+ ListView)
    Button       :: @+id/btn_config - Configuration button
    View         :: @+id/sep_line - sepration line (Optional)
    View         :: @+id/event_conflicts - Event conflicts (Required for single event skins)

#### Row layout
Details for one event
Location: /res/layout/skin_row.xml

Predefined views

    TextView :: @+id/event_date - Event date
    TextView :: @+id/event_color - Color of Event (Optional)
    TextView :: @+id/event_title - Title of event
    TextView :: @+id/event_times - Times of event
    TextView :: @+id/event_location - Location of event

#### Row No Events layout
Visible when no events found
Location: /res/layout/skin_row_noevents.xml

Predefined views

    TextView :: @+id/no_events_text - Text: no events found

Compatibility
--------------

