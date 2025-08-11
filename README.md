
## TWRP device tree Samsung Galaxy A56 5G SM-A566B (a56x)

## Flash Steps
You can find the guide in the download area.
 
## Build Steps
Assuming you know the basic of preparing build environment...
* TWRP Source:
```
repo init --depth=1 -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
```
```
sed -i '/<remove-project name="platform\/external\/gflags"  \/>/d' .repo/manifests/remove-minimal.xml
```
```
repo sync -j$(nproc --all) --force-sync
```
* Device Tree (Make sure you are in root directory of TWRP source.):
```
git clone https://github.com/ratatouille100/twrp_device_samsung_a56x -b dev ./device/samsung/a56x
```
* Build (Make sure you are in root directory of TWRP source.)
```
source build/envsetup.sh; export ALLOW_MISSING_DEPENDENCIES=true; lunch twrp_a56x-eng; mka vendorbootimage
```
* Check `vendor_boot.img` in $OUT directory.

## Credits
- [cd-Crypton](https://github.com/cd-Crypton)
- The [custom_recovery_tree_samsung_a55x](https://github.com/cdpcrp/custom_recovery_tree_samsung_a55x) repo
- [Samsung Open Source](https://opensource.samsung.com/)
- [Android Open Source Project](https://source.android.com/)
- [The Linux Kernel](https://www.kernel.org/)
