cmake_minimum_required(VERSION 2.8.3)
project(mil_tasks)
find_package(catkin REQUIRED genmsg actionlib_msgs actionlib)
catkin_python_setup()
add_action_files(
  FILES
    DoTask.action
)
generate_messages(
  DEPENDENCIES
    std_msgs
    actionlib_msgs
)
catkin_package()

if(CATKIN_ENABLE_TESTING)
    find_package(rostest REQUIRED)
    add_rostest(test/import_mil_tasks_examples.test)
endif()
