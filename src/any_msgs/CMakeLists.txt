# Minimum cmake version
cmake_minimum_required(VERSION 2.8.3)

# Create project
project(any_msgs)

# Find catkin macros and libraries
find_package(catkin REQUIRED
  COMPONENTS
    std_msgs
    message_generation
)

# Declare the message and service files to be built
add_message_files(
  FILES
    Event.msg
    State.msg
)
add_service_files(
  FILES
    ProcessFile.srv
    Toggle.srv
    SetUInt32.srv 
    SetFloat64.srv 
)
generate_messages(
  DEPENDENCIES
    std_msgs
)

# Generate a package
catkin_package(
  CATKIN_DEPENDS
    std_msgs
    message_runtime
)
