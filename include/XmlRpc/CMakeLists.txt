set(xmlrpc_headers
XmlRpc.h
XmlRpcClient.h
XmlRpcDispatch.h
XmlRpcException.h
XmlRpcServer.h
XmlRpcServerConnection.h
XmlRpcServerMethod.h
XmlRpcSocket.h
XmlRpcSource.h
XmlRpcUtil.h
XmlRpcValue.h
base64.h
)

set(xmlrpc_hdrs)
foreach(a IN ITEMS ${xmlrpc_headers})
  list(APPEND xmlrpc_hdrs include/XmlRpc/${a})
endforeach()

set(xmlrpcxx_hdrs_ ${xmlrpc_hdrs} PARENT_SCOPE)
