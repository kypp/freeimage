set (MODULE_NAME freeimage)

if (!BUILD_SHARED_LIBS)
	add_definitions(-DFREEIMAGE_LIB -DLIBRAW_NODLL -DOPJ_STATIC)
endif(!BUILD_SHARED_LIBS)

include_directories (.. ../ZLib ../DeprecationManager ../OpenEXR ../OpenEXR/Half ../OpenEXR/Iex ../OpenEXR/IlmImf ../OpenEXR/Imath ../OpenEXR/IlmThread ../LibJXR/jxrgluelib ../LibJXR/image/sys)

file (GLOB ${MODULE_NAME}_SRCS *.cpp ../DeprecationManager/*.cpp ../FreeImageToolkit/*.cpp ../Metadata/*.cpp )

add_library (${MODULE_NAME} ${${MODULE_NAME}_SRCS})

install (TARGETS ${MODULE_NAME} 
		ARCHIVE DESTINATION lib 
		LIBRARY DESTINATION lib)