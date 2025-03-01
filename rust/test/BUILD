load(
    "//rust:defs.bzl",
    "rust_cc_proto_library",
    "rust_proto_library",
    "rust_upb_proto_library",
)
load("@rules_cc//cc:defs.bzl", "cc_proto_library")

UNITTEST_PROTO_TARGET = "//src/google/protobuf:test_protos"

UNITTEST_CC_PROTO_TARGET = "//src/google/protobuf:cc_test_protos"

UNITTEST_PROTO3_TARGET = "//src/google/protobuf:test_protos"

UNITTEST_PROTO3_CC_TARGET = "//src/google/protobuf:cc_test_protos"

UNITTEST_PROTO3_OPTIONAL_TARGET = "//src/google/protobuf:test_protos"

UNITTEST_PROTO3_OPTIONAL_CC_TARGET = "//src/google/protobuf:cc_test_protos"

alias(
    name = "unittest_cc_proto",
    actual = UNITTEST_CC_PROTO_TARGET,
    visibility = ["//rust/test:__subpackages__"],
)

rust_proto_library(
    name = "unittest_rust_proto",
    testonly = True,
    visibility = [
        "//visibility:private",  # Only private by automation, not intent. Owner may accept CLs adding visibility. See go/scheuklappen#explicit-private.
    ],
    deps = [UNITTEST_PROTO_TARGET],
)

rust_upb_proto_library(
    name = "unittest_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [UNITTEST_PROTO_TARGET],
)

rust_cc_proto_library(
    name = "unittest_cc_rust_proto",
    testonly = True,
    visibility = [
        "//rust/test/cpp:__subpackages__",
        "//rust/test/shared:__subpackages__",
    ],
    deps = [UNITTEST_CC_PROTO_TARGET],
)

rust_proto_library(
    name = "unittest_proto3_rust_proto",
    testonly = True,
    visibility = [
        "//visibility:private",  # Only private by automation, not intent. Owner may accept CLs adding visibility. See go/scheuklappen#explicit-private.
    ],
    deps = [
        UNITTEST_PROTO3_TARGET,
    ],
)

rust_cc_proto_library(
    name = "unittest_proto3_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [UNITTEST_PROTO3_CC_TARGET],
)

rust_upb_proto_library(
    name = "unittest_proto3_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [UNITTEST_PROTO3_TARGET],
)

rust_proto_library(
    name = "unittest_proto3_optional_rust_proto",
    testonly = True,
    visibility = [
        "//visibility:private",  # Only private by automation, not intent. Owner may accept CLs adding visibility. See go/scheuklappen#explicit-private.
    ],
    deps = [
        UNITTEST_PROTO3_OPTIONAL_TARGET,
    ],
)

rust_cc_proto_library(
    name = "unittest_proto3_optional_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [UNITTEST_PROTO3_OPTIONAL_CC_TARGET],
)

rust_upb_proto_library(
    name = "unittest_proto3_optional_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [UNITTEST_PROTO3_OPTIONAL_TARGET],
)

proto_library(
    name = "parent_proto",
    srcs = ["parent.proto"],
)

proto_library(
    name = "child_proto",
    testonly = True,
    srcs = ["child.proto"],
    exports = [":parent_proto"],
    deps = [":parent_proto"],
)

rust_upb_proto_library(
    name = "parent_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":parent_proto"],
)

rust_upb_proto_library(
    name = "child_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":child_proto"],
)

cc_proto_library(
    name = "parent_cc_proto",
    testonly = True,
    deps = [":parent_proto"],
)

cc_proto_library(
    name = "child_cc_proto",
    testonly = True,
    deps = [":child_proto"],
)

rust_cc_proto_library(
    name = "parent_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":parent_cc_proto"],
)

rust_cc_proto_library(
    name = "child_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":child_cc_proto"],
)

proto_library(
    name = "dots_in_package_proto",
    testonly = True,
    srcs = ["dots_in_package.proto"],
)

cc_proto_library(
    name = "dots_in_package_cc_proto",
    testonly = True,
    deps = [":dots_in_package_proto"],
)

rust_cc_proto_library(
    name = "dots_in_package_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":dots_in_package_cc_proto"],
)

rust_upb_proto_library(
    name = "dots_in_package_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":dots_in_package_proto"],
)

proto_library(
    name = "edition2023_proto",
    testonly = True,
    srcs = ["edition2023.proto"],
)

cc_proto_library(
    name = "edition2023_cc_proto",
    testonly = True,
    deps = [":edition2023_proto"],
)

rust_cc_proto_library(
    name = "edition2023_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":edition2023_cc_proto"],
)

rust_upb_proto_library(
    name = "edition2023_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":edition2023_proto"],
)

proto_library(
    name = "enums_proto",
    testonly = True,
    srcs = ["enums.proto"],
    deps = ["//devtools/staticanalysis/pipeline/analyzers/proto_best_practices/proto:optouts_proto"],
)

cc_proto_library(
    name = "enums_cc_proto",
    testonly = True,
    deps = [":enums_proto"],
)

rust_cc_proto_library(
    name = "enums_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":enums_cc_proto"],
)

rust_upb_proto_library(
    name = "enums_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":enums_proto"],
)

proto_library(
    name = "no_package_import_proto",
    testonly = True,
    srcs = ["no_package_import.proto"],
)

proto_library(
    name = "no_package_proto",
    testonly = True,
    srcs = [
        "no_package.proto",
        "no_package_other.proto",
    ],
    exports = [":no_package_import_proto"],
    deps = [":no_package_import_proto"],
)

cc_proto_library(
    name = "no_package_cc_proto",
    testonly = True,
    deps = [":no_package_proto"],
)

rust_cc_proto_library(
    name = "no_package_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":no_package_cc_proto"],
)

rust_upb_proto_library(
    name = "no_package_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":no_package_proto"],
)

proto_library(
    name = "package_import_proto",
    testonly = True,
    srcs = ["package_import.proto"],
)

proto_library(
    name = "package_proto",
    testonly = True,
    srcs = [
        "package.proto",
        "package_other.proto",
        "package_other_different.proto",
    ],
    exports = [":package_import_proto"],
    deps = [":package_import_proto"],
)

cc_proto_library(
    name = "package_cc_proto",
    testonly = True,
    deps = [":package_proto"],
)

rust_cc_proto_library(
    name = "package_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":package_cc_proto"],
)

rust_upb_proto_library(
    name = "package_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":package_proto"],
)

proto_library(
    name = "reserved_proto",
    testonly = True,
    srcs = ["reserved.proto"],
)

cc_proto_library(
    name = "reserved_cc_proto",
    testonly = True,
    deps = [":reserved_proto"],
)

rust_cc_proto_library(
    name = "reserved_cc_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":reserved_cc_proto"],
)

rust_upb_proto_library(
    name = "reserved_upb_rust_proto",
    testonly = True,
    visibility = ["//rust/test/shared:__subpackages__"],
    deps = [":reserved_proto"],
)

proto_library(
    name = "nested_proto",
    testonly = True,
    srcs = ["nested.proto"],
)

cc_proto_library(
    name = "nested_cc_proto",
    testonly = True,
    deps = [":nested_proto"],
)

rust_cc_proto_library(
    name = "nested_cc_rust_proto",
    testonly = True,
    visibility = [
        "//rust/test/cpp:__subpackages__",
        "//rust/test/shared:__subpackages__",
    ],
    deps = [":nested_cc_proto"],
)

rust_upb_proto_library(
    name = "nested_upb_rust_proto",
    testonly = True,
    visibility = [
        "//rust/test/shared:__subpackages__",
        "//rust/test/upb:__subpackages__",
    ],
    deps = [":nested_proto"],
)

cc_proto_library(
    name = "map_unittest_cc_proto",
    testonly = True,
    deps = ["//src/google/protobuf:map_unittest_proto"],
)

rust_cc_proto_library(
    name = "map_unittest_cc_rust_proto",
    testonly = True,
    visibility = [
        "//rust/test/shared:__subpackages__",
    ],
    deps = [":map_unittest_cc_proto"],
)

rust_upb_proto_library(
    name = "map_unittest_upb_rust_proto",
    testonly = True,
    visibility = [
        "//rust/test/shared:__subpackages__",
    ],
    deps = ["//src/google/protobuf:map_unittest_proto"],
)
