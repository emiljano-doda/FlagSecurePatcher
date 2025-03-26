## Magisk Flag Secure Patcher
Magisk module to patch services jars on device using dexlib2 to stop apps from preventing taking screenshots and block screenshot listeners that was introduced back in Android 14.\
This module should work in Android 15

Based on github.com/j-hc/FlagSecurePatcher\
Fixed Error when installing on android 15\
Changed line 48 in customize.sh to specify api level 34 in order to get a v40 dex which works fine\
Code Change :
```
if ! OP=$(paccer "$DEX" "$DEX" "$TARGET_JAR_NAME" 34 2>&1); then
```
Old  Code   :
```
if ! OP=$(paccer "$DEX" "$DEX" "$TARGET_JAR_NAME" "$API" 2>&1); then
```
(from here https://github.com/google/smali/blob/main/dexlib2/src/main/java/com/android/tools/smali/dexlib2/VersionMap.java)

Friendly Reminder : remember to uninstall the module before doing a system update