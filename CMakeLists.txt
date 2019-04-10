CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

    PROJECT(ccpp-vscode)

    set(CMAKE_CC_FLAGS "${CMAKE_CC_FLAGS} -Wall -pedantic -g -Wextra")
    
    # HELLO C
    add_library(helloc SHARED src/c/hello.c)
    ADD_EXECUTABLE(helloc-exe src/c/main.c )
    TARGET_LINK_LIBRARIES(helloc-exe helloc)

    # HELLO CPP
    set(CMAKE_CXX_STANDARD 11)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -pedantic -g -Wextra")
    add_library(hellocpp SHARED src/cpp/hello.cpp)
    ADD_EXECUTABLE(hellocpp-exe src/cpp/main.cpp)
    TARGET_LINK_LIBRARIES(hellocpp-exe hellocpp)
