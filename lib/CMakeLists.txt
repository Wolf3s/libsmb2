set(SOURCES alloc.c
            errors.c
            init.c
            libsmb2.c
            pdu.c
            smb2-cmd-close.c
            smb2-cmd-create.c
            smb2-cmd-echo.c
            smb2-cmd-error.c
            smb2-cmd-flush.c
            smb2-cmd-logoff.c
            smb2-cmd-negotiate.c
            smb2-cmd-query-directory.c
            smb2-cmd-query-info.c
            smb2-cmd-read.c
            smb2-cmd-session-setup.c
            smb2-cmd-set-info.c
            smb2-cmd-tree-connect.c
            smb2-cmd-tree-disconnect.c
            smb2-cmd-write.c
            smb2-data-file-info.c
            smb2-data-security-descriptor.c
            socket.c
            sync.c
            timestamps.c
            unicode.c)

add_library(smb2 ${SOURCES})
target_link_libraries(smb2 PUBLIC ${core_DEPENDS})
set_target_properties(smb2 PROPERTIES
                           VERSION ${PROJECT_VERSION}
                           SOVERSION ${SOVERSION})
add_definitions("-D_U_=__attribute__((unused))")

install(TARGETS smb2 EXPORT smb2
                     RUNTIME DESTINATION bin
                     ARCHIVE DESTINATION lib
                     LIBRARY DESTINATION lib)