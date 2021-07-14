#
# Component Makefile
#

set (includes)
set (srcs)
set (priv_includes)

list(APPEND includes
    "aws-iot-device-sdk-embedded-C/demos/ota/common/include/"
    "aws-iot-device-sdk-embedded-C/demos/pkcs11/common/include/"
    "aws-iot-device-sdk-embedded-C/libraries/aws/device-shadow-for-aws-iot-embedded-sdk/source/include"
    "aws-iot-device-sdk-embedded-C/libraries/aws/jobs-for-aws-iot-embedded-sdk/source/include"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/include"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/portable"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/portable/os/"
    "aws-iot-device-sdk-embedded-C/libraries/standard/backoffAlgorithm/source/include/"
    "aws-iot-device-sdk-embedded-C/libraries/standard/coreJSON/source/include"
    "aws-iot-device-sdk-embedded-C/libraries/standard/coreMQTT/source/include"
    "aws-iot-device-sdk-embedded-C/libraries/standard/coreMQTT/source/interface"
    "aws-iot-device-sdk-embedded-C/libraries/standard/corePKCS11/source/dependency/3rdparty/mbedtls_utils/"
    "aws-iot-device-sdk-embedded-C/libraries/standard/corePKCS11/source/dependency/3rdparty/pkcs11/"
    "aws-iot-device-sdk-embedded-C/libraries/standard/corePKCS11/source/include/"
    "aws-iot-device-sdk-embedded-C/platform/include/"
    "port/crypto/"
    "port/include"
    "port/logging"
    "port/mqtt_helpers"
    "port/network_transport"
    "port/ota/"
    "port/posix-compat/"
    )

list(APPEND srcs
    "aws-iot-device-sdk-embedded-C/demos/ota/common/src/mqtt_subscription_manager.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/device-shadow-for-aws-iot-embedded-sdk/source/shadow.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/jobs-for-aws-iot-embedded-sdk/source/jobs.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src/cborencoder.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src/cborencoder_close_container_checked.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src/cborerrorstrings.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src/cborparser.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src/cborparser_dup_string.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src/cborpretty.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/dependency/3rdparty/tinycbor/src/cborpretty_stdio.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/ota.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/ota_base64.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/ota_cbor.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/ota_interface.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/ota_mqtt.c"
    "aws-iot-device-sdk-embedded-C/libraries/aws/ota-for-aws-iot-embedded-sdk/source/portable/os/ota_os_freertos.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/backoffAlgorithm/source/backoff_algorithm.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/coreJSON/source/core_json.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/coreMQTT/source/core_mqtt.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/coreMQTT/source/core_mqtt_serializer.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/coreMQTT/source/core_mqtt_state.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/corePKCS11/source/core_pki_utils.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/corePKCS11/source/dependency/3rdparty/mbedtls_utils/mbedtls_error.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/corePKCS11/source/portable/mbedtls/core_pkcs11_mbedtls.c"
    "aws-iot-device-sdk-embedded-C/libraries/standard/corePKCS11/source/portable/posix/core_pkcs11_pal.c"
    "aws-iot-device-sdk-embedded-C/platform/posix/clock_posix.c"
    "port/crypto/iot_crypto.c"
    "port/mqtt_helpers/mqtt_demo_helpers.c"
    "port/network_transport/tls_freertos.c"
    "port/ota/aws_esp_ota_ops.c"
    "port/ota/ota_pal.c"
    "port/posix-compat/semaphore.c"
    )

idf_component_register(SRCS "${srcs}"
                    INCLUDE_DIRS ${includes}
                    PRIV_INCLUDE_DIRS ${priv_includes}
                    REQUIRES lwip nghttp mbedtls tcp_transport spi_flash bootloader_support app_update)
