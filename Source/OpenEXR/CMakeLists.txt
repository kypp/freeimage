set (MODULE_NAME libopenexr)

if (!BUILD_SHARED_LIBS)
	add_definitions(-D_LIB)
endif(!BUILD_SHARED_LIBS)

include_directories (. IlmImf Imath IexMath Iex Half IlmThread ../ZLib)

file (GLOB ${MODULE_NAME}_SRCS half/*.cpp Iex/*.cpp IexMath/*.cpp IlmImf/*.cpp IlmThread/*.cpp Imath/*.cpp)

add_library (${MODULE_NAME} ${${MODULE_NAME}_SRCS})

install (TARGETS ${MODULE_NAME} 
		ARCHIVE DESTINATION lib 
		LIBRARY DESTINATION lib)