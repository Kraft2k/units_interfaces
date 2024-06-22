cmake_minimum_required(VERSION 3.5)
project(units_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "action/UpFrontServo.action"
  "action/ReachMarker.action"
  "action/DetectMarker.action"
  "srv/SetUnitMode.srv"
  "srv/ResetOdometry.srv"
  "srv/GetOdometry.srv"
  "srv/SetSpeed.srv"
  "srv/GoToXYTheta.srv"
  "srv/DistanceToGoal.srv"
  "srv/IsGoToFinished.srv"
  "srv/GetBatteryVoltage.srv"
  "srv/GetUnitMode.srv"
  "srv/SetUnitSafety.srv"
  "srv/SetFrontLights.srv"
  )

ament_export_dependencies(rosidl_default_runtime)

ament_package()
