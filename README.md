## ReSPlay
---
A cross-platform record-and-replay tool for mobile apps

All the evaluation artifacts are available here, which include tools, apps we used, and instructions about how to run the tool on mobile phones. Details can be found in our paper. It is a useful record-and-replay tool, which leverages a most robust visual feature, GUI sequences, to guide replaying more accurately.

#### Framework
![Framework](https://github.com/anonymousCSCode/ReSPlay/blob/main/Figures/oview.png)
---

## All Experimental Apps
---
The selected apps are Keep, Booking, Amazon Shopping, Evernote, App Music, Kindle, AdGuard, HERE WeGo, Tricount, Wikipedia, Monkey, and openHAB. The categories they belong to include health & fitness, travel, shopping, productivity, music, books, personalization, tools, finance, news, development, and lifestyle.
Experimental apps are available to download from [this link](https://drive.google.com/file/d/161DLXEDe7S4WPCPOzCVDpiZQBMzdoeTR/view?usp=sharing).

---
## Instructions
---
#### ADB Install
Step 1. Get the latest SDK platform-tools from Android Studio's [SDK Manager](https://developer.android.com/studio/intro/update#sdk-manager) or from the [sdkmanager](https://developer.android.com/studio/command-line/sdkmanager) command-line tool. Once you’ve downloaded the Platform Tools package, extract the contents of the .zip file to a folder (like “C:\Android\platform-tools”).
Step 2. Configure your PATH Variable. The PATH variable is a master list of where to look for command line tools.
#### Windows
Depending on which version of Windows you’re using, these steps may be slightly different. To add ADB to your PATH variable, follow these steps:

1. Open the Start menu and search for “advanced system settings.”
2. Click “View advanced system settings.”
3. Click the box that says “Environment Variables.”
4. Under “System variables” click on the variable named “Path”.
5. Click “Edit...”
6. (Windows 7,8): Add ;[FOLDERNAME] to the end of the “Variable value” box, replacing [FOLDERNAME] with the folder path where you extracted Platform Tools. Be sure to include the semicolon at the beginning so Windows knows you’re adding a new folder.
7. (Windows 10): Click “New” and paste the folder path where you extracted the Platform Tools. Hit Enter and click OK.

#### MacOS/Linux
1. Open up a Terminal window by navigating to Applications/Utilities or searching for it in Spotlight.
2. Enter the following command to open up your Bash profile: touch ~/.bash_profile; open ~/.bash_profile
3. The .bash_profile file should open in your default text program.
4. Add this line to the end of the file: export PATH=”$HOME/[FOLDERNAME]/bin:$PATH” replacing [FOLDERNAME] with the location where you extracted ADB and fastboot.
5. Save the file and press Cmd+Q to quit your text editor.
6. In your terminal enter source ~/.bash_profile to run your Bash profile for the first time.
