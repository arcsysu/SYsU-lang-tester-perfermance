FILE(GLOB mains *.sysu.c)
FOREACH(mainfile ${mains})
    # Get file name without directory
    GET_FILENAME_COMPONENT(mainname ${mainfile} NAME_WE)
    ADD_EXECUTABLE(sysu-tester-performance_${mainname} ${mainfile})
    TARGET_LINK_LIBRARIES(sysu-tester-performance_${mainname} sysy)
    TARGET_INCLUDE_DIRECTORIES(sysu-tester-performance_${mainname} PRIVATE ${CMAKE_SOURCE_DIR}/librarian)
    INSTALL(TARGETS sysu-tester-performance_${mainname})
ENDFOREACH()