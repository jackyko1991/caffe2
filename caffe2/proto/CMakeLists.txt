# uncomment following two lines if you use custom build protobuf
# find_package(Protobuf REQUIRED)
# include_directories(${PROTOBUF_INCLUDE_DIRS})

file(GLOB Caffe2_PROTOBUF_FILES "${CMAKE_CURRENT_SOURCE_DIR}/*.proto")

caffe2_protobuf_generate_cpp_py(Caffe2_PROTO_SRCS Caffe2_PROTO_HEADERS Caffe2_PROTO_PY ${Caffe2_PROTOBUF_FILES})

add_library(Caffe2_PROTO OBJECT ${Caffe2_PROTO_HEADERS} ${Caffe2_PROTO_SRCS})
install(FILES ${Caffe2_PROTO_HEADERS} DESTINATION include/caffe2/proto)
