cmake_minimum_required(VERSION 3.5)
project(nimbro_api_interfaces)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ApiUsage.msg"
  "msg/Embedding.msg"

  "srv/CompletionsGetContext.srv"
  "srv/CompletionsGetSettings.srv"
  "srv/CompletionsGetStatus.srv"
  "srv/CompletionsGetTools.srv"
  "srv/CompletionsManage.srv"
  "srv/CompletionsPrompt.srv"
  "srv/CompletionsRemoveContext.srv"
  "srv/CompletionsSetTools.srv"
  "srv/CompletionsStop.srv"

  "srv/GetEmbeddings.srv"
  "srv/GetImage.srv"
  "srv/GetNimbroVision.srv"
  "srv/GetSpeech.srv"
  "srv/GetUsage.srv"
  "srv/TriggerFeedback.srv"

  DEPENDENCIES std_msgs sensor_msgs
)

ament_package()
