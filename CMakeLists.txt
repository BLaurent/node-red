cmake_minimum_required(VERSION 2.8)
SET(BUILD_PATH ${CMAKE_CURRENT_SOURCE_DIR})
SET(DOCKER_TAG "blaurent/node-red")
SET(CONTAINER_NAME node-red)
SET(TAG_RELEASE "blaurent/node-red")


add_custom_target(build_arm
  COMMAND docker build ${build_args} --tag=${DOCKER_TAG}:arm -f arm/Dockerfile .
  WORKING_DIRECTORY ${BUILD_PATH})

add_custom_target(build_x86
  COMMAND docker build ${build_args} --tag=${DOCKER_TAG} -f x86/Dockerfile .
  WORKING_DIRECTORY ${BUILD_PATH})


