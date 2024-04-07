cmake_minimum_required(VERSION 2.8.9)
project(CmakeSample)

if (WIN32)
    set(INCLUDE_DIRECTORIES
        C:/opencv-3.2.0/build/include)
    set(LINK_DIRECTORIES
        C:/opencv-3.2.0/build/x64/vc14/lib)
    set(TARGET_LINK_LIBRARIES_RELEASE
        optimized opencv_core320.lib
        optimized opencv_highgui320.lib
        optimized opencv_imgcodecs320.lib
        optimized opencv_imgproc320.lib)
    set(TARGET_LINK_LIBRARIES_DEBUG
        debug opencv_core320d.lib
        debug opencv_highgui320d.lib
        debug opencv_imgcodecs320d.lib
        debug opencv_imgproc320d.lib)
elseif (UNIX)
    set(INCLUDE_DIRECTORIES
        /usr/local/include)
    set(LINK_DIRECTORIES
        /usr/local/lib)
    set(TARGET_LINK_LIBRARIES_RELEASE
        optimized libopencv_core.so
        optimized libopencv_highgui.so
        optimized libopencv_imgcodecs.so
        optimized libopencv_imgproc.so)
    set(TARGET_LINK_LIBRARIES_DEBUG
        debug libopencv_core.so
        debug libopencv_highgui.so
        debug libopencv_imgcodecs.so
        debug libopencv_imgproc.so)
else ()
    
endif ()

include_directories(
    ${INCLUDE_DIRECTORIES}
)

link_directories(
    ${LINK_DIRECTORIES}
)

add_executable(CmakeSample
    Source.c
    Header.h
)

target_link_libraries(CmakeSample
    ${TARGET_LINK_LIBRARIES_RELEASE}
    ${TARGET_LINK_LIBRARIES_DEBUG}
)
