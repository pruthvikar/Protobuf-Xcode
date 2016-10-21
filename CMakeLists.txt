cmake_minimum_required(VERSION 3.6)
project(Protobuf)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

include_directories(include)

set(SOURCE_FILES
    src/arena.cc
    src/arenastring.cc
    src/atomicops_internals_x86_gcc.cc
    src/atomicops_internals_x86_msvc.cc
    src/bytestream.cc
    src/coded_stream.cc
    src/common.cc
    src/extension_set.cc
    src/generated_message_util.cc
    src/int128.cc
    src/message_lite.cc
    src/once.cc
    src/repeated_field.cc
    src/status.cc
    src/statusor.cc
    src/stringpiece.cc
    src/stringprintf.cc
    src/structurally_valid.cc
    src/strutil.cc
    src/time.cc
    src/wire_format_lite.cc
    src/zero_copy_stream.cc
    src/zero_copy_stream_impl_lite.cc)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DHAVE_ZLIB -DHAVE_PTHREAD")

add_library (protobuf-lite SHARED ${SOURCE_FILES})