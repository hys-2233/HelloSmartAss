cmake_minimum_required(VERSION 3.10)
project(client)

set(CMAKE_CXX_STANDARD 17)
find_package(Protobuf REQUIRED)

message(STATUS "Protobuf libraries: ${Protobuf_LIBRARIES}")
message(STATUS "Protobuf include directory: ${Protobuf_INCLUDE_DIRS}")

add_executable(client client.cpp helloworld.pb.cc helloworld.grpc.pb.cc)
target_link_libraries(client grpc++ ${PROTOBUF_LIBRARY})
