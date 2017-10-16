cmake_minimum_required(VERSION 2.8)
SET(DEVSHELL_PATH ${CMAKE_CURRENT_SOURCE_DIR})
SET(DEVSHELL_TAG "blaurent/node-red")
SET(DEVSHELL_CONTAINER_NAME node-red)
SET(TAG_RELEASE "blaurent/node-red")


add_custom_target(build_arm
  COMMAND docker build ${build_args} --tag=${DEVSHELL_TAG}:arm -f arm/Dockerfile .
  WORKING_DIRECTORY ${DEVSHELL_PATH})

add_custom_target(build_x86
  COMMAND docker build ${build_args} --tag=${DEVSHELL_TAG} -f x86/Dockerfile .
  WORKING_DIRECTORY ${DEVSHELL_PATH})


