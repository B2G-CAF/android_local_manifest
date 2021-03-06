Local manifests to build CAF Firefox OS for [ZTE Open C / Kis 3](http://konstakang.com/devices/kis3/FirefoxOS) and [Motorola Moto G](http://konstakang.com/devices/falcon/FirefoxOS).

How to build:
-------------

Initialize repo:

    repo init -u git://codeaurora.org/quic/lf/manifest.git -b release -m LNX.LF.3.5.1-11900-8x10.0.xml
    curl --create-dirs -L -o .repo/local_manifests/local_manifest.xml -O -L https://raw.githubusercontent.com/B2G-CAF/android_local_manifest/b2g_kk_3.5/local_manifest.xml
    repo sync

### ZTE Open C / Kis 3:

    curl -L -o .repo/local_manifests/manifest_zte_kis3.xml -O -L https://raw.githubusercontent.com/B2G-CAF/android_local_manifest/b2g_kk_3.5/manifest_zte_kis3.xml
    repo sync

Compile:

    . build/envsetup.sh
    . device/qcom/b2g_common/vendorsetup.sh force
    lunch kis3-userdebug
    make

### Motorola Moto G:

    curl -L -o .repo/local_manifests/manifest_motorola_falcon.xml -O -L https://raw.githubusercontent.com/B2G-CAF/android_local_manifest/b2g_kk_3.5/manifest_motorola_falcon.xml
    repo sync

Compile:

    . build/envsetup.sh
    . device/qcom/b2g_common/vendorsetup.sh force
    lunch falcon-userdebug
    make
