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



include_directories(${CMAKE_SOURCE_DIR}/include/${PROJECT_NAME})


add_library(${PROJECT_NAME} SHARED ${xmlrpc_srcs})
set_target_properties(${PROJECT_NAME}
  PROPERTIES
  ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
  LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
  RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)

