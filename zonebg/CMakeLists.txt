# CMakeLists for zonebg/ directory
#
# Installs default "zone background" files

FILE(GLOB zonebg "${CMAKE_CURRENT_SOURCE_DIR}/*.png" "${CMAKE_CURRENT_SOURCE_DIR}/*.jpg")

if(UNIX)
    if(APPLE)
      	INSTALL(FILES ${zonebg} DESTINATION cockatrice.app/Contents/Resources/zonebg/)
    else()
        # Assume linux
        INSTALL(FILES ${zonebg} DESTINATION share/cockatrice/zonebg/)
    endif()
elseif(WIN32)
    INSTALL(FILES ${zonebg} DESTINATION zonebg/)
endif()