cmake_minimum_required(VERSION 3.5)

add_subdirectory(tools)

add_subdirectory(kernel)

set(CMAKE_VERBOSE_MAKEFILE on)

add_compile_options(-m32 -g -Wall)


add_executable(test_init tests/init.c)
target_link_libraries(test_init netinet tool)
set_target_properties(test_init PROPERTIES LINK_FLAGS "-m32")

add_executable(test_pigeon tests/pigeon.c)
target_link_libraries(test_pigeon netinet tool)
set_target_properties(test_pigeon PROPERTIES LINK_FLAGS "-m32")

add_executable(test_tun tests/tun.c)
target_link_libraries(test_tun netinet tool)
set_target_properties(test_tun PROPERTIES LINK_FLAGS "-m32")

add_executable(test_self tests/self.c)
target_link_libraries(test_self netinet tool)
set_target_properties(test_self PROPERTIES LINK_FLAGS "-m32")