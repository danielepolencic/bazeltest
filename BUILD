load("@npm//@bazel/typescript:index.bzl", "ts_library")
load("@build_bazel_rules_nodejs//:index.bzl", "nodejs_binary")

exports_files([
    "tsconfig.json",
    "package.json",
])

ts_library(
    name = "universal_server_lib",
    srcs = [
        "index.ts",
    ],
    deps = [
        "//packages/a",
        "//packages/b",
    ],
)

nodejs_binary(
    name = "universal_server",
    data = [
        ":universal_server_lib",
    ],
    entry_point = ":index.ts",
)