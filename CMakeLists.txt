cmake_minimum_required(VERSION 3.5)

project(uFTP LANGUAGES C)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(SRCS
    ftpCommandElaborate.c
    ftpData.c
    ftpServer.c
    library/auth.c
    library/configRead.c
    library/connection.c
    library/daemon.c
    library/dynamicMemory.c
    library/dynamicVectors.c
    library/errorHandling.c
    library/fileManagement.c
    library/logFunctions.c
    library/openSsl.c
    library/signals.c
    uFTP.c
    )

set(HEADERS
    ftpCommandsElaborate.h
    ftpData.h
    ftpServer.h
    ftpSpecs.h
    library/auth.h
    library/configRead.h
    library/connection.h
    library/daemon.h
    library/dynamicMemory.h
    library/dynamicVectors.h
    library/errorHandling.h
    library/fileManagement.h
    library/logFunctions.h
    library/openSsl.h
    library/signals.h
    )

add_executable(uFTP
    ${SRCS}
    ${HEADERS}
)

target_link_libraries(uFTP PRIVATE -lpthread)
