cmake_minimum_required(VERSION 2.4)
project(VDFS)

file(GLOB SRC
    *.cpp
    *.h
)

add_library(vdfs STATIC ${SRC})

# Remove WIN-API min and max macros since they mess up std::min/max
if(MSVC)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /DNOMINMAX")
endif()


set_target_properties(vdfs PROPERTIES LINKER_LANGUAGE C)
