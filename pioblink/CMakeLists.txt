add_executable(${PROJECT_NAME})

pico_generate_pio_header(${PROJECT_NAME} ${CMAKE_CURRENT_LIST_DIR}/blink.pio)

target_sources(${PROJECT_NAME} PRIVATE blink.c)

target_include_directories(${PROJECT_NAME} PUBLIC
        .
        ${CMAKE_CURRENT_LIST_DIR}/../build/pioblink)

target_link_libraries(${PROJECT_NAME} PRIVATE
        pico_stdlib
        hardware_pio
        )

pico_add_extra_outputs(${PROJECT_NAME})

# add url via pico_set_program_url
# example_auto_set_url(hello_pio)
