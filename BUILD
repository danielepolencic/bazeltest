load("@npm//@bazel/typescript:index.bzl", "ts_library")
load("@build_bazel_rules_nodejs//:index.bzl", "nodejs_binary")
load("@io_bazel_rules_docker//nodejs:image.bzl", "nodejs_image")
load("@io_bazel_rules_docker//container:container.bzl", "container_image")

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

filegroup(
    name = "mainfile",
    srcs = ["universal_server_lib"],
    output_group = "es5_sources",
)

nodejs_image(
    name = "server",
    data = [
        ":universal_server_lib",
    ],
    entry_point = ":mainfile",
)
