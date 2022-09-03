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
1. Check and Modify the Config File.

Minor amendments to the config file are required, which include deviceName, pkName, activityName, res_x, and res_y.
deviceName:
```
adb devices
```
res_x and res_y indicate the device resolution in the x and y dimensions. 
```
adb shell wm size
```
pkName and activityName represent package name and lunchable activity name of apps:
```
adb shell dumpsys window | findstr "mCurrentFocus"
```
2. Start the record process, which will log GUI screenshots and widget screenshots.
```
python getPosition.py
```


  
