cmake_minimum_required(VERSION 3.25)
project(ZzzTorrent)

set(CMAKE_CXX_STANDARD 17)

add_executable(ZzzTorrent main.cpp)

# libtorrent-rasterbar
include_directories(${LIBTORRENT_INCLUDE_DIRS})
link_directories(${LIBTORRENT_LIB_DIRS})
target_link_libraries(ZzzTorrent /opt/homebrew/Cellar/libtorrent-rasterbar/2.0.9_4/lib/libtorrent-rasterbar.dylib)

# Boost
set(Boost_INCLUDE_DIR /opt/homebrew/Cellar/boost/1.83.0/include)
find_package(Boost REQUIRED COMPONENTS system thread)
set(Boost_LIBRARY_DIR /opt/homebrew/Cellar/boost/1.83.0/lib)
include_directories(${Boost_INCLUDE_DIR})
target_link_libraries(ZzzTorrent ${Boost_LIBRARIES})