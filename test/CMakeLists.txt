message( STATUS ${CMAKE_SOURCE_DIR} )

include_directories( ${CMAKE_SOURCE_DIR}/src )

add_executable( AllTests
    AllTests.cpp
    FooTest.cpp
)

target_link_libraries( AllTests
    Foo
    ${GTEST_LIBRARY}
    ${Boost_LIBRARIES}
)
