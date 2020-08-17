load("@npm//@bazel/typescript:index.bzl", "ts_library")

package(default_visibility = ["//visibility:public"])

ts_library(
    name = "b",
    srcs = ["index.ts"],
    deps = [
        "//packages/a",
    ],
    # module_name = "@core/b",
)
