cmake_minimum_required(VERSION 2.8.3)
project(cob_moveit_config)

find_package(catkin REQUIRED)

catkin_package()

set(robotlist
    cob4-2
    cob4-5
    cob4-7
    raw3-1
)

foreach(robot ${robotlist})
    install(DIRECTORY ${robot}
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
    )
endforeach()

install(DIRECTORY launch DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})

install(PROGRAMS bin/add_robot.sh DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
