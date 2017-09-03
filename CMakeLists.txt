cmake_minimum_required(VERSION 3.7)
project(cppsimu)

set(CMAKE_CXX_STANDARD 11)

INCLUDE_DIRECTORIES(/usr/local/libevent2/include )

LINK_DIRECTORIES(/usr/local/libevent2/lib)


set(SOURCE_FILES
        src/agv/agvsimu.cpp)

set(BOOST_ROOT /usr/local/boost159/)

set(Boost_USE_STATIC_LIBS        ON) # only find static libs
set(Boost_USE_MULTITHREADED      ON)
set(Boost_USE_STATIC_RUNTIME    OFF)

find_package(Boost  COMPONENTS system filesystem REQUIRED)

if(Boost_FOUND)

    message(STATUS "Boost_INCLUDE_DIRS: ${Boost_INCLUDE_DIRS}")
    message(STATUS "Boost_LIBRARIES: ${Boost_LIBRARIES}")
    message(STATUS "Boost_VERSION: ${Boost_VERSION}")


    include_directories(${Boost_INCLUDE_DIRS})

endif()



if(Boost_FOUND)
    add_executable(cppsimu ${SOURCE_FILES})
    target_link_libraries(cppsimu ${Boost_LIBRARIES})

endif()

