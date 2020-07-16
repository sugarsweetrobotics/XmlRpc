include_directories(${CMAKE_SOURCE_DIR}/include/${PROJECT_NAME})



function(add_test NAME)
  add_executable(${NAME} ${NAME}.cpp)
  target_link_libraries(${NAME} ${PROJECT_NAME})
  set_target_properties(${NAME}
    PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin" 
  )
endfunction(add_test)

add_test(FileClient)
add_test(HelloClient)
add_test(HelloServer)
add_test(TestXml)
add_test(TestValues)
add_test(TestBase64Server)
add_test(TestBase64Client)
add_test(Validator)
