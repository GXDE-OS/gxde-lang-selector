# Install resources/ folder, excluding desktop file and icons.

install(FILES ${CMAKE_CURRENT_SOURCE_DIR}/session.wrapper
        DESTINATION ${CMAKE_INSTALL_PREFIX}/lib/gxde-lang-selector/
        PERMISSIONS
        OWNER_READ OWNER_EXECUTE OWNER_WRITE
        GROUP_READ GROUP_EXECUTE
        WORLD_READ WORLD_EXECUTE
        )

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/gxde-lang-selector-launcher.in
               ${CMAKE_CURRENT_BINARY_DIR}/gxde-lang-selector-launcher
               @ONLY)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/gxde-lang-selector-launcher
        DESTINATION ${CMAKE_INSTALL_PREFIX}/lib/gxde-lang-selector/
        PERMISSIONS
        OWNER_READ OWNER_EXECUTE OWNER_WRITE
        GROUP_READ GROUP_EXECUTE
        WORLD_READ WORLD_EXECUTE
        )

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/gxde-lang-selector.service.in
               ${CMAKE_CURRENT_BINARY_DIR}/gxde-lang-selector.service
               @ONLY)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/gxde-lang-selector.service
        DESTINATION ${CMAKE_INSTALL_PREFIX}/lib/systemd/system
        )
