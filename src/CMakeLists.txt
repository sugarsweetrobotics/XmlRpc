set(xmlrpc_srcs
XmlRpcClient.cpp
XmlRpcDispatch.cpp
XmlRpcServer.cpp
XmlRpcServerConnection.cpp
XmlRpcServerMethod.cpp
XmlRpcSocket.cpp
XmlRpcSource.cpp
XmlRpcUtil.cpp
XmlRpcValue.cpp
)



include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../include/${PROJECT_NAME})


foreach(a IN ITEMS ${xmlrpcxx_headers})
  list(APPEND xmlrpc_hdrs ${PROJECT_SOURCE_DIR}/${a})
endforeach()

if (WIN32)
set(CMAKE_DEBUG_POSTFIX d)
endif (WIN32)

add_library(${PROJECT_NAME} SHARED ${xmlrpc_srcs} ${xmlrpc_hdrs})
set_target_properties(${PROJECT_NAME}
  PROPERTIES
  ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
  LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
  RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)

if (WIN32)
# install(FILES "${CMAKE_BINARY_DIR}/lib/Debug/${PROJECT_NAME}d.lib"
#  DESTINATION "lib/")
install(FILES "${CMAKE_BINARY_DIR}/bin/Debug/${PROJECT_NAME}d.dll" 
  DESTINATION "bin/")
endif (WIN32)

