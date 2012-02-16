cmake_minimum_required(VERSION 2.8)
project(genpybindings)

find_package(catkin)

add_subdirectory(scripts)

catkin_stack()
catkin_project(genpybindings
  CFG_EXTRAS genpybindings-extras.cmake
)

file(WRITE ${CMAKE_CURRENT_BINARY_DIR}/genpybindings "Boost.Python bindings to C++")
install(FILES stack.yaml DESTINATION share/${PROJECT_NAME})
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/genpybindings
  DESTINATION etc/langs
  )

