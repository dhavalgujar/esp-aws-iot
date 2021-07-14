set(COMPONENT_SRCS "app_main.c" "ota_demo_core_mqtt.c")
set(COMPONENT_ADD_INCLUDEDIRS ".")

idf_component_register(SRCS "${COMPONENT_SRCS}"
					   INCLUDE_DIRS ${COMPONENT_ADD_INCLUDEDIRS}
					  )
