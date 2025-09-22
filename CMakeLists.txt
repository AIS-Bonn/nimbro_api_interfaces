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
  "msg/Embedding.msg"

  "srv/CompletionsContextGet.srv"
  "srv/CompletionsContextSet.srv"
  "srv/CompletionsManage.srv"
  "srv/CompletionsPrompt.srv"
  "srv/CompletionsSettingsGet.srv"
  "srv/CompletionsStatusGet.srv"
  "srv/CompletionsToolsGet.srv"
  "srv/CompletionsToolsSet.srv"
  "srv/CompletionsInterrupt.srv"

  "srv/EmbeddingsGet.srv"
  "srv/ImagesGet.srv"
  "srv/NimbroVisionGet.srv"
  "srv/SpeechGet.srv"
  "srv/TriggerFeedback.srv"
  "srv/UsageGet.srv"

  DEPENDENCIES std_msgs sensor_msgs
)

ament_package()
