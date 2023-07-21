list(APPEND ex
    simple/simple.cpp
)

# message(STATUS "yivo::Examples ----------------------")
foreach(src ${ex})
    get_filename_component(name ${src} NAME_WE)
    # message(STATUS " -> ${name}")
    add_executable(${name} ${src})
    target_link_libraries(${name} ${PROJECT_NAME})
    add_test(NAME ${name} COMMAND ${name})
endforeach()