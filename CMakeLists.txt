cmake_minimum_required(VERSION 2.8.3)
project(ros_google_sbi)

find_package(catkin REQUIRED COMPONENTS rospy message_generation std_msgs sensor_msgs)

add_message_files(DIRECTORY msg FILES DescriptionTags.msg WordOccurrence.msg)
add_service_files(DIRECTORY srv FILES NameItGoogle.srv)

generate_messages(DEPENDENCIES std_msgs sensor_msgs)

catkin_package(CATKIN_DEPENDS message_runtime std_msgs)

#add_dependencies(${PROJECT_NAME} ${PROJECT_NAME}_genpy)

# do not wildcard install files since the root folder of the package will contain a debian folder for releasing
catkin_install_python(PROGRAMS
  py_google_sbi/google_sbi_tagit.py
  py_google_sbi/snapshot.py
  ros_google_sbi/google_name_it
  ros_google_sbi/nameit_client
  launch/sbi.launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
