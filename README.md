# Xcode Developer Disk Image for iOS 4.2 and Above

Download ZIP: [https://github.com/xushuduo/Xcode-iOS-Developer-Disk-Image/releases](https://github.com/xushuduo/Xcode-iOS-Developer-Disk-Image/releases)

Path: `/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport`

Tip: Restart the Xcode


## Frida stuff 

```shell
$ frida-ps -Uai
Failed to enumerate applications: this feature requires an iOS Developer Disk Image to be mounted; run Xcode briefly or use ideviceimagemounter to mount one manually

$ idevicepair pair
ERROR: Please accept the trust dialog on the screen of device 75f3b2a[...]97617b9, then attempt to pair again.

$ idevicepair pair
SUCCESS: Paired with device 75f3b2a[...]97617b9

# Navigate to the image disk you downloaded
$ cd 14.3\ (18C65)

$ deviceimagemounter DeveloperDiskImage.dmg DeveloperDiskimage.dmg.signature

Uploading DeveloperDiskImage.dmg
done.
Mounting...
Done.
Status: Complete

$ frida-ps -Uai
  PID  Name                 Identifier
-----  -------------  -------------------------------------
39608  Calendar       com.apple.mobilecal
39679  Cydia          com.saurik.Cydia
39680  App Store      com.apple.AppStore
[...]
```
