cmake_minimum_required(VERSION 3.1)
project(quickjs)

set(quickjs_sources_root ${CMAKE_CURRENT_SOURCE_DIR})
set(quickjs_sources
	${quickjs_sources_root}/quickjs.h
	${quickjs_sources_root}/quickjs-libc.h
	${quickjs_sources_root}/quickjs.c
	${quickjs_sources_root}/libregexp.c
	${quickjs_sources_root}/libunicode.c
	${quickjs_sources_root}/libbf.c
	${quickjs_sources_root}/cutils.c
	${quickjs_sources_root}/quickjs-libc.c
)



add_library(${PROJECT_NAME}
	${quickjs_sources}
)
target_compile_definitions(${PROJECT_NAME} PRIVATE
		CONFIG_VERSION="2021-03-27"
)
target_include_directories(${PROJECT_NAME}
	PUBLIC
		${quickjs_sources_root}
)