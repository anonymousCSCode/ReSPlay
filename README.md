## ReSPlay
---
A cross-platform record-and-replay tool for mobile apps

All the evaluation artifacts are available here, which include tools, apps we used, and instructions about how to run the tool on mobile phones. Details can be found in our paper. It is a useful record-and-replay tool, which leverages a most robust visual feature, GUI sequences, to guide replaying more accurately.

#### Framework:
![Framework](https://github.com/anonymousCSCode/ReSPlay/blob/main/Figures/oview.png)
---

## All Experimental Apps
---
The selected apps are Keep, Booking, Amazon Shopping, Evernote, App Music, Kindle, AdGuard, HERE WeGo, Tricount, Wikipedia, Monkey, and openHAB. The categories they belong to include health & fitness, travel, shopping, productivity, music, books, personalization, tools, finance, news, development, and lifestyle.
Experimental apps are available to download from [this link](https://drive.google.com/file/d/161DLXEDe7S4WPCPOzCVDpiZQBMzdoeTR/view?usp=sharing).

## Environment settings
---
  * Python 3.9.6
  * ADB
  * Appium
  
#### Step One: ADB Install
1. Get the Latest SDK Platform-tools From Android Studio's [SDK Manager](https://developer.android.com/studio/intro/update#sdk-manager) or From the [Sdkmanager](https://developer.android.com/studio/command-line/sdkmanager) Command-line Tool. Once you’ve downloaded the Platform Tools package, extract the contents of the .zip file to a folder (like “C:\Android\platform-tools”).

2. Configure the PATH Variable. The PATH variable is a master list of where to look for command line tools. For details, please refer to [this link](https://lifehacker.com/the-easiest-way-to-install-androids-adb-and-fastboot-to-1586992378).

3. Enable USB Debugging on Mobile Phones.

4. Test ADB (if Needed).
The third and fourth steps can refer to [this link](https://www.howtogeek.com/125769/how-to-install-and-use-abd-the-android-debug-bridge-utility/).

#### Step Two: Appium Install
  The installation process can refer to [this link](https://appium.io/docs/en/about-appium/getting-started/?lang=en).

#### Step Three: Dependency Library Installation  
  Run `pip install -r requirements.txt` to install the Python libraries:
  
#### Step Four: Setup App
  Install the app on the mobile device
  ```
  adb install XXX.apk
  ```
## Record (UIRecorder)
---
The recoding phase aims to synchronously extract critical information from input events to provide support for sebsequent analysis. Specifically, ReSPlay records GUI screenshots, layout files, and widget screenshots. 

Users such as developers or testers perform a series of operations on mobile devices. Each operation will be responded to by the device's sensors in real-time and sent to the kernel in the form of event streams. The absolute position information for each operation is then identified and extracted. For instance, such events are stored in an external device file `/dev/input/event*` for the Android platform. 

The operated widget is found based on the recorded hierarchies and extracted coordinates using a recursive method. Widget screenshots are cropped from GUI screenshots based on widget coordinates.

**The process of the recording phase is as follows.**

1. Check and Modify the Config File.

Minor amendments to the config file are required, which include `deviceName`, `pkName`, `activityName`, `res_x`, and `res_y`. `res_x` and `res_y` indicate the device resolution in the x and y dimensions. `pkName` and `activityName` represent package name and lunchable activity name of apps.

To retrieve the `deviceName`, `res_x`, `res_y`, `pkName`, and `activityName`, run the following commands:
```
deviceName: adb devices
resolution: adb shell wm size
package and activity name: adb shell dumpsys window | findstr "mCurrentFocus"
```
2. Start the recording process.
```
python getPosition.py
```

**After the abovementioned processes, some necessary contents are automatically parsed and stored in a nested directory.**

The directories named with the package name contain five folders/scenarios, each of which includes widget screenshots (see Figure 2), layout files (see Figure 3), and GUI screenshots (see Figure 4).


#### Figure 2:
![figure2](https://github.com/anonymousCSCode/ReSPlay/blob/main/Figures/widget_screenshots.jpg)

#### Figure 3:
![figure3](https://github.com/anonymousCSCode/ReSPlay/blob/main/Figures/layout_files.jpg)

#### Figure 4:
![figure4](https://github.com/anonymousCSCode/ReSPlay/blob/main/Figures/GUI_screenshots.jpg)


## Replay (SDP-Net)
---
#### Step One: Move recorded `traces` of UIRecorder to `imageFile` directory of SDP-Net.

#### Step Two: Start training.
1. Start an Appium server.

```
python train.py
```
#### Step Three:. Start the replaying phase.
```
python inference.py
```
