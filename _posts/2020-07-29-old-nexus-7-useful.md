---
layout: post
title:  "Making An Old Nexus 7(2012) Useful In 2020"
date:   2020-07-29 17:45:20
category: blog post
---

# Introduction
If for some reason you are holding on to this old tablet, and refuse to upgrade to an iPad like a normal person, here are some steps you can take to my make your old tablet more useful. The Nexus 7 was unfortunatley left with a slow unusuable version of Android Lollipop (5.1.1) before it was discontinued but, there is an easy way to fix that and even run Android Nougat

# Important Notes 

- Make sure any important data, cat pictures, etc is backed up safely off your tablet. The following steps will require completely wiping the tablet. 

- Modifications made to your tablet may prevent it from passing SafetyNet checks. ie: Netflix may not show up in the playstore.

- Most of these instructions will be for the model I own the Nexus 7 (2012) Wifi aka Grouper but many should apply to the Nexus 7(2012) 3G as well. If you're unsure check the XDA Forums.

# Requirements

- A usb micro cable
- Time
- A Computer With Win, Mac or Linux


# Rooting

## Prequisites
- [adb platform-tools](https://developer.android.com/studio/releases/platform-tools)
- [TWRP (Prefereably 3.4.0)](https://dl.twrp.me/grouper/)
- (Optional) [SuperSU 2.82](https://s3-us-west-2.amazonaws.com/supersu/download/zip/SuperSU-v2.82-201705271822.zip)


## Steps

1. Make sure usb debugging is enabled. If it is not already go in to Setting About and press the Build Number 5 Times until it says you are a developer. Then In your developer options settings make sure USB debuggin is also turned on. This will look slightly different from these screenshots. [Put Screenshots here]

![settings](/assets/old-nexus-7-useful/Screenshot_20200729-190004.png)
![developer_options](/assets/old-nexus-7-useful/Screenshot_20200729-190144.png)

2. Make sure you are open a terminal or command prompt in the directory of the adb platform-tools. run 


        abd reboot bootloader 
        fastboot oem unlock
        

3. Flash TWRP (the guide from XDA says to use CWM (clockwork mod) but it should make no difference until later) then run 

        
        fastboot flash recovery path-to-img/twrp-grouper-recovery.img
        

4. Enter recovery 

    
        adb reboot recovery
    

5. Mount /system

![mount](/assets/old-nexus-7-useful/Screenshot_2020-07-29-19-33-02.png)

6. Type in Terminal 
    
        adb shell
        cd /system
        mv recovery-from-boot.p recovery-from-boot.bak

    

7. If you want to stop here install SuperSU from the link above and reboot into android 5.1.1.
Otherwise, proceed to the next section.





# Flashing a Custom Rom

## Prerequisites 
- (Optional) [Magisk](https://github.com/topjohnwu/Magisk/releases/download/v20.4/Magisk-v20.4.zip)
- [AndDiSa's Android 7.X AOSP Port](https://forum.xda-developers.com/nexus-7/development/rom-android-7-aosp-grouper-t3467514)
- [GAPPS Pico](https://opengapps.org/) 

## Steps

1. Factory reset through TWRP

2. Install the newest version of the AOSP. I recommend the one linked above as it includes built in optimizations that have made my tablet run smoother than how it ran on an older cutom rom.

3. (Optional if you don't want GAPPS aka playstore, etc) Reboot to Recovery and install the linked GAPPs package

4. (Optional if you don't want root) download Magisk from the link above and install it with TWRP

# Sources 

- [https://forum.xda-developers.com/showthread.php?t=1741395](https://forum.xda-developers.com/showthread.php?t=1741395)
- [https://forum.xda-developers.com/nexus-7/development/rom-android-7-aosp-grouper-t3467514](https://forum.xda-developers.com/nexus-7/development/rom-android-7-aosp-grouper-t3467514)