package(default_visibility=["//visibility:public"])

load("@rules_cc//cc:defs.bzl", "cc_proto_library")
load("@rules_proto//proto:defs.bzl", "proto_library")
load("@com_google_protobuf//:protobuf.bzl", "py_proto_library")

proto_library(
    name = "beancount_proto",
    srcs = ["beancount.proto"],
    deps = [
      ## "@com_google_protobuf//src/google/protobuf/any.proto",
    ],
)

cc_proto_library(
    name = "beancount_cc_proto",
    deps = [
      ":beancount_proto",
    ],
)

py_proto_library(
    name = "beancount_py_proto",
    srcs = ["beancount.proto"],
    #deps = [":beancount_proto"],
)

py_binary(
    name = "export_as_protos",
    srcs = ["export_as_protos.py"],
    deps = [
        ":beancount_py_proto",
        "@com_google_riegeli//python/riegeli",
    ],
)
