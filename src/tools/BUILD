#
#  Copyright (c) 2020 NetEase Inc.
#
#  Licensed under the Apache License, Version 2.0 (the "License");
#  you may not use this file except in compliance with the License.
#  You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
#  Unless required by applicable law or agreed to in writing, software
#  distributed under the License is distributed on an "AS IS" BASIS,
#  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#  See the License for the specific language governing permissions and
#  limitations under the License.
#

load("//:copts.bzl", "CURVE_DEFAULT_COPTS")

cc_binary(
    name = "curve_format",
    srcs = [
        "curve_format_main.cpp",
    ],
    copts = CURVE_DEFAULT_COPTS,
    deps = [
        "//external:braft",
        "//external:brpc",
        "//external:bthread",
        "//external:butil",
        "//external:bvar",
        "//external:gflags",
        "//external:glog",
        "//external:json",
        "//external:protobuf",
        "//proto:chunkserver-cc-protos",
        "//src/chunkserver:chunkserver-lib",
        "//src/common:curve_common",
        "//src/fs:lfs",
    ],
)

cc_binary(
    name = "curve_tool",
    srcs = ["curve_tool_main.cpp"],
    copts = CURVE_DEFAULT_COPTS,
    visibility = ["//visibility:public"],
    deps = [
        "//external:gflags",
        "//src/tools:curve_tool_lib",
    ],
)

cc_binary(
    name = "curve_chunkserver_tool",
    srcs = ["chunkserver_tool_main.cpp"],
    copts = CURVE_DEFAULT_COPTS,
    visibility = ["//visibility:public"],
    deps = [
        "//external:braft",
        "//external:gflags",
        "//src/tools:curve_tool_lib",
    ],
)

cc_library(
    name = "curve_tool_lib",
    srcs = glob(
        ["*.cpp"],
        exclude = [
            "curve_tool_main.cpp",
            "curve_format_main.cpp",
            "createtool.cpp",
            "chunkserver_tool_main.cpp",
        ],
    ),
    hdrs = glob([
        "*.h",
    ]),
    copts = CURVE_DEFAULT_COPTS,
    visibility = ["//visibility:public"],
    deps = [
        "//external:braft",
        "//external:brpc",
        "//external:bthread",
        "//external:butil",
        "//external:bvar",
        "//external:gflags",
        "//external:glog",
        "//external:leveldb",
        "//external:protobuf",
        "//include/chunkserver:include-chunkserver",
        "//include/client:include_client",
        "//proto:chunkserver-cc-protos",
        "//proto:nameserver2_cc_proto",
        "//proto:schedule_cc_proto",
        "//proto:topology_cc_proto",
        "//src/chunkserver:chunkserver-lib",
        "//src/client:curve_client",
        "//src/common:curve_common",
        "//src/mds/common:mds_common",
        "//src/mds/nameserver2",
        "@com_google_absl//absl/strings:str_format",
    ],
)
