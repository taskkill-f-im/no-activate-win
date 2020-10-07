
Do not get overwhelmed by this. It is easy and saves you $100.

# Get rid of watermark:
I find the watermark comes back after 5 hours, but I don't notice it unless I watch something on fullscreen  
When you want to game, just run this and the watermark won't be there when you play fullscreen.  
  
Put this in a .bat file and run it when you want to restart:
  > taskkill /f /im explorer.exe  
  > start explorer.exe  
  > pause  
  > shutdown /r /t 0  

  To download if you are too lazy (You are safe, do not worry, but check anyways): On github, Go to "Code" (Green), then "Download ZIP" It will be in files\refreshWin.bat  
To check its contents, right click and press edit. The text inside should be the same displayed here.

# Have the personalization back on control panel:
Actually, most of the settings are available here but I found it pretty buggy. I don't think you can change the taskbar and accent color with this though. 
[https://winaero.com/personalization-control-panel-windows-10/](https://winaero.com/personalization-control-panel-windows-10/)  


# Registry Edits:
To open regedit: Open start menu, type 'regedit', press enter.   
**If some keys do not exist for you, right-click and create a new DWORD containing the "key." The keys have to be spelled correctly and capitalized where shown. (The keys are the things we have to change. In this post, they will be bolded and in quotations for easier to read format). Changing the key means to change the 'Value Data'.**
![](https://github.com/taskkill-f-im/no-activate-win/blob/main/files/regedit_add_new.png)

**Some changes are not instant, you have to restart. You can restart after you made all the changes. Even though the chances of you breaking your computer are low, I have to say be careful.**

* Change wallpaper location:
  1. Go to \[HKEY\_CURRENT\_USER\\Control Panel\\Desktop\]
  2. Find the key named **"Wallpaper"** and change 'Value Data' to whatever path your image is, put it in quotes.  
If you are more advanced, you can find the default windows image at "C:\\Windows\\Web\\Wallpaper\\Windows\\img0.jpg", take ownership of the file (Winaero Tweaker provides an easy guide to do this), modify its content using mspaint (copy & paste is probably the easiest)
![](https://github.com/taskkill-f-im/no-activate-win/blob/main/files/regedit_example.PNG)

* Change lock screen image:
  1. Go to \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Personalization\]  
Change **"LockScreenImage"** = whatever path you want, put it quotes   
If that didn't work, this article worked for me, **look at the post with 20 upvotes**: [https://superuser.com/questions/1126403/what-is-the-location-of-lock-screen-images-on-windows-10](https://superuser.com/questions/1126403/what-is-the-location-of-lock-screen-images-on-windows-10)
* Bonus: Disable Windows Spotlight 
  1. \[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen\]  
**"SlideshowEnabled"** = 0  
  2. \[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager\]  
**"RotatingLockScreenEnabled"** = 0  
**"RotatingLockScreenOverlayEnabled"** = 0  

* Make wallpaper at 100% quality (default is 75% quality, yea Microsoft is crazy)  
  \[HKEY\_CURRENT\_USER\\Control Panel\\Desktop\]  
  Change **"JPEGImportQuality"** to 64 (hex for 100)

* Dark mode:  
  [HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize\]  
**"AppsUseLightTheme"** = change to 0  
**"SystemUsesLightTheme"** = 0  
**"SpecialColor"** = 00010101  

* Customize color of the window title bar   
  1. \[HKEY\_CURRENT\_USER\\Control Panel\\Desktop\]    
**"AutoColorization"** = 0   
  2. Below are my settings. They make the windows/startmenu/taskbar fully blacked out on top. I do not remember some of these as I applied them a long time ago. These are all necessary to change them. To use colors other than black, you can use [https://www.w3schools.com/colors/colors\_picker.asp](https://www.w3schools.com/colors/colors_picker.asp)   
[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\DWM\]   
**"ColorizationColor"** =dword: ff010101   
**"ColorizationAfterglow"** =dword: c44c4a48   
Title bars/taskbar/startmenu color: **"AccentColor"** =dword: 171717   
... when clicked away: **"AccentColorInactive"** =dword: 00303030   
To make title bars a different color from white: **"ColorPrevalence"** =dword: 00000001   
**"ColorizationGlassAttribute"** =dword: 00000000  
  3. \[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent\]  
**"StartColorMenu"**=dword:ff010101  
**"AccentColorMenu"**=dword:ff010101
