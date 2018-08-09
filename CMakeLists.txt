cmake_minimum_required(VERSION 3.5.1)
project(Protobuf)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

include_directories(include)

set(SOURCE_FILES
    src/int128.cc
    src/structurally_valid.cc
    src/generated_message_table_driven_lite.cc
    src/zero_copy_stream_impl_lite.cc
    src/status.cc
    src/arena.cc
    src/zero_copy_stream_impl.cc
    src/coded_stream.cc
    src/common.cc
    src/message_lite.cc
    src/wire_format_lite.cc
    src/zero_copy_stream.cc
    src/repeated_field.cc
    src/atomicops_internals_x86_gcc.cc
    src/implicit_weak_message.cc
    src/bytestream.cc
    src/io_win32.cc
    src/statusor.cc
    src/arenastring.cc
    src/generated_message_util.cc
    src/atomicops_internals_x86_msvc.cc
    src/strutil.cc
    src/stringprintf.cc
    src/time.cc
    src/extension_set.cc
    src/stringpiece.cc)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DHAVE_ZLIB -DHAVE_PTHREAD")

add_library (protobuf-lite SHARED ${SOURCE_FILES})