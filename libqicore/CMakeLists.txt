## Copyright (c) 2012, 2014 Aldebaran Robotics. All rights reserved.

include_directories(".")

set(PUBLIC_HEADERS
    qicore/api.hpp
    #qicore/behavior.hpp
    qicore/loglistener.hpp
    qicore/logmanager.hpp
    qicore/logmessage.hpp
    qicore/logprovider.hpp
    )
install(FILES ${PUBLIC_HEADERS} DESTINATION ${CATKIN_GLOBAL_INCLUDE_DESTINATION}/qicore)

add_library(qicore
  ${PUBLIC_HEADERS}
  #src/behavior.cpp src/behaviormodel.cpp src/format_behavior_model.cpp
  src/loglistener_proxy.cpp
  src/logmanager_proxy.cpp
  src/logprovider_proxy.cpp
  src/logproviderimpl.cpp
  src/logproviderimpl.hpp
)

target_link_libraries(qicore ${Boost_LIBRARIES} ${catkin_LIBRARIES})
install(TARGETS qicore DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})

#add_subdirectory("tests")
