# Google Pixel VOLTE & safetynet-fix

구글 픽셀 Magisk 설치, VOLTE 패치, safetynet 검사 우회



## Driver, QPST setting

[Google Driver](https://developer.android.com/studio/run/win-usb)

[QPST](https://qpsttool.com/category/download)



## Google Factory Img

boot.img 추출 후 magisk에서 패치, 다시 fastboot에서 install.



["bullhead" for Nexus 5X](https://developers.google.com/android/images#bullhead)

["sargo" for Pixel 3a](https://developers.google.com/android/images#sargo)

["barbet" for Pixel 5a](https://developers.google.com/android/images#barbet)



## SDK Platform

[SDK  Platform - Android Developers](https://developer.android.com/studio/releases/platform-tools)



## Magisk

[Magisk Repository](https://github.com/topjohnwu/Magisk)



## VOLTE

VOLTE 패치를 원한다면 parasite, EFS 파일 다운로드.

[parasite.sh](https://github.com/nooriro/parasite)

[efs - kr](https://github.com/nooriro/efs-kr-sunfish)



*Special thanks to [nooriro](https://github.com/nooriro)*



## Commands

[매지스크 설치, 어렵지 않아요](https://cafe.naver.com/grnf/336178)

[픽셀 3~4~5 VoLTE 가이드](https://cafe.naver.com/grnf/337896)



바탕화면에 diag 폴더가 있을 경우

`cd Desktop\diag`

`adb install app-release.apk`

`adb push boot.img /sdcard/Download/`

`adb install app-release.apk`



### If using parasite(VOLTE)

`adb push parasite.sh /data/local/tmp/ && adb shell chmod u+x /data/local/tmp/parasite.sh`

`adb shell /data/local/tmp/parasite.sh`

`adb reboot bootloader && fastboot boot magisk_patched_diag.img`



#### diag open

`adb shell`

`su -c "setenforce 0; setprop sys.usb.configfs 1 && setprop sys.usb.config diag,serial_cdev,rmnet_gsi,adb"`

쉘에 루트 권한 부여 후 EFS Explorer를 이용, 파일 덮어씌우기

`adb shell su -c setprop persist.dbg.volte_avail_ovr 1`



### Just Magisk only

`adb reboot bootloader`

`fastboot boot magisk_patched_diag.img`

**DONE!**



## Universal SafetyNet Fix

[Safetynet Repository](https://github.com/kdrag0n/safetynet-fix)

[SafetyNet 검사 우회](https://cafe.naver.com/grnf)

