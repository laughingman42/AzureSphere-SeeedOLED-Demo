#  Copyright (c) Microsoft Corporation. All rights reserved.
#  Licensed under the MIT License.

cmake_minimum_required (VERSION 3.10)

project (AzureSphere-SeeedOLED-Demo C)

azsphere_configure_tools(TOOLS_REVISION "21.04")
azsphere_configure_api(TARGET_API_SET "9")

# Create executable
add_executable (${PROJECT_NAME} main.c "hwlibs/seeedoled.c" "hwlibs/seeedoled.h")
target_link_libraries (${PROJECT_NAME} applibs pthread gcc_s c)

azsphere_target_hardware_definition(${PROJECT_NAME} TARGET_DEFINITION "seeed_mt3620_mdb.json")

azsphere_target_add_image_package(${PROJECT_NAME})
