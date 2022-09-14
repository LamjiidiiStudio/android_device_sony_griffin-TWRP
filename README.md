# Unified TWRP Device Tree for Sony Xperia 1 (griffin)

The Sony Xperia 1 (codenamed "griffin") is a flagship smartphone from Sony Xperia. It was announced in February 25 2019 and released in May 30 2019.

## Device specifications

| Feature                 | Specification                                                                |
| :---------------------- | :----------------------------------------------------------------------------|
| Chipset                 | Qualcomm SM8150 Snapdragon 855 (7 nm)                                        |
| CPU                     | Octa-core (1x2.84 GHz Kryo 485 & 3x2.42 GHz Kryo 485 & 4x1.78 GHz Kryo 485)  |
| GPU                     | Adreno 640                                                                   |
| Memory                  | 6 GB                                                                     |
| Shipped Android Version | 9.0 (Pie), upgradable to 11 (Eleven)                                                                |
| Storage                 | 64/128 GB UFS 2.1                                                            |
| SIM                     | Single SIM (Nano-SIM) or Hybrid Dual SIM (Nano-SIM, dual stand-by)                                           |
| MicroSD                 | microSDXC (uses shared SIM slot) - dual SIM model only                                                                 |
| Battery                 | Li-Ion 3330 mAh, non-removable                                               |
| Dimensions              | 167 x 72 x 8.2 mm (6.57 x 2.83 x 0.32 in)                                                       |
| Display                 | OLED, HDR BT.2020, 6.5 inches, 98.6 cm2 (~82.0% screen-to-body ratio), 1644 x 3840 pixels, 21:9 ratio (~643 ppi density)                                         |
| Rear Camera 1           | 12 MP, f/1.6, 26mm (wide), 1/2.55", 1.4µm, predictive Dual Pixel PDAF, 5-axis OIS                               |
| Rear Camera 2           | 12 MP, f/2.4, 52mm (telephoto), 1/3.4", 1.0µm, predictive PDAF, 2x optical zoom, 5-axis OIS                                |
| Rear Camera 3           | 12 MP, f/2.4, 16mm (ultrawide), 1/3.4", 1.0µm                                         |
| Front Camera            | 8 MP, f/2.0, 24mm (wide), 1/4", 1.12µm                                         |
| Fingerprint             | side-mounted                                                                 |
| Sensors                 | accelerometer, gyro, proximity, barometer, compass, color spectrum                                      |

## Device picture

![Sony Xperia 1](https://fdn2.gsmarena.com/vv/pics/sony/sony-xperia-1-1.jpg)


For building TWRP for Sony Xperia 1

TWRP device tree for Sony Xperia 1

## Features

Works:

- Stil in testing

TO-DO:

- .

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/griffin" name="LamjiidiiStudio/android_device_sony_griffin-TWRP" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_griffin-eng
export ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
mka bootimage
```

To test it:

```
fastboot boot out/target/product/griffin/boot.img
```

## Enjoy.