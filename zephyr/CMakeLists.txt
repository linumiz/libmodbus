if(CONFIG_LIBMODBUS)

zephyr_include_directories(../src /home/parthiban/work/west/native/modules/lib/w5500/ /home/parthiban/work/west/native/modules/lib/w5500/ /home/parthiban/work/west/native/modules/lib/w5500/Ethernet/W5500)
zephyr_library()

zephyr_library_sources(
	../src/modbus.c
	../src/modbus-data.c
)
zephyr_library_sources_ifdef(
	CONFIG_LIBMODBUS_TCP ../src/modbus-tcp.c)
zephyr_library_sources_ifdef(
	CONFIG_LIBMODBUS_RTU ../src/modbus-rtu.c)

endif()
