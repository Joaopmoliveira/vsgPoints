set(SOURCES
    ConvertMeshToPoints.cpp
    vsgpoints.cpp
)

add_executable(vsgpoints ${SOURCES})

target_link_libraries(vsgpoints vsg::vsg vsgPoints::vsgPoints)

if (vsgXchange_FOUND)
    target_compile_definitions(vsgpoints PRIVATE vsgXchange_FOUND)
    target_link_libraries(vsgpoints vsgXchange::vsgXchange)
endif()

install(TARGETS vsgpoints RUNTIME DESTINATION bin)
