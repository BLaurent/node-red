cmake_minimum_required(VERSION 2.8)
SET(DEVSHELL_PATH ${CMAKE_CURRENT_SOURCE_DIR})
SET(DEVSHELL_TAG "blaurent/node-red-docker")
SET(DEVSHELL_CONTAINER_NAME node-red-docker)
SET(TAG_RELEASE "blaurent/node-red-docker")


add_custom_target(build_arm
  COMMAND docker build ${build_args} --tag=${DEVSHELL_TAG}:arm -f Dockerfile.arm .
  WORKING_DIRECTORY ${DEVSHELL_PATH})

add_custom_target(build_x86
  COMMAND docker build ${build_args} --tag=${DEVSHELL_TAG} -f Dockerfile.x86 .
  WORKING_DIRECTORY ${DEVSHELL_PATH})


