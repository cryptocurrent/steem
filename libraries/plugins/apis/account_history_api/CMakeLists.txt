file(GLOB HEADERS "include/steemit/plugins/account_history_api/*.hpp")
add_library( account_history_api_plugin
             account_history_api_plugin.cpp
             account_history_api.cpp
           )

target_link_libraries( account_history_api_plugin account_history_plugin json_rpc_plugin )
target_include_directories( account_history_api_plugin PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include" )

install( TARGETS
   account_history_api_plugin

   RUNTIME DESTINATION bin
   LIBRARY DESTINATION lib
   ARCHIVE DESTINATION lib
)
