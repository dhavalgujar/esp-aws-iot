# Steps to run OTA Demo

1. Apply the patch file aws-iot-device-sdk-embedded-C.patch available in the root, to the SDK submodule.  

2. Copy `threading_alt.h` from `port/crypto` file to `~/esp/esp-idf/components/mbedtls/port/include/`
```sh
cp port/crypto/threading_alt.h ~/esp/esp-idf/components/mbedtls/port/include/
```

4. `idf.py menuconfig` and set MQTT endpoint.

5. `idf.py build flash monitor`