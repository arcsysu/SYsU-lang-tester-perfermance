FILE(GLOB mains *.sysu.c)
FOREACH(mainfile ${mains})
    # Get file name without directory
    GET_FILENAME_COMPONENT(mainname ${mainfile} NAME_WE)
    ADD_EXECUTABLE(sysu-tester-performance_test2021-public_${mainname} ${mainfile})
    TARGET_LINK_LIBRARIES(sysu-tester-performance_test2021-public_${mainname} sysy)
    TARGET_INCLUDE_DIRECTORIES(sysu-tester-performance_test2021-public_${mainname} PRIVATE ${CMAKE_SOURCE_DIR}/librarian)
    INSTALL(TARGETS sysu-tester-performance_test2021-public_${mainname})
ENDFOREACH()