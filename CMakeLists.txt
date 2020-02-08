cmake_minimum_required(VERSION 2.8)

PROJECT(relayd C)
ADD_DEFINITIONS(-Os -Wall -Werror --std=gnu99 -g3)

ADD_EXECUTABLE(relayd main.c dhcp.c route.c uloop.c utils.c)
TARGET_LINK_LIBRARIES(relayd)

SET(CMAKE_INSTALL_PREFIX /usr/local/bin)

INSTALL(TARGETS relayd
	RUNTIME DESTINATION sbin
)
