package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["generator.go"],
    visibility = ["//mixer/tools:__subpackages__"],
    deps = [
        "//mixer/tools/codegen/pkg/interfacegen/template:go_default_library",
        "//mixer/tools/codegen/pkg/modelgen:go_default_library",
        "@com_github_gogo_protobuf//proto:go_default_library",
        "@com_github_gogo_protobuf//protoc-gen-gogo/descriptor:go_default_library",
        "@org_golang_x_tools//imports:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    size = "small",
    srcs = ["generator_test.go"],
    data = [
        "//mixer/tools/codegen/pkg/interfacegen/testdata/apa:descriptor_set",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/apa:golden_files",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/check:descriptor_set",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/check:golden_files",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/error:baseline",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/error:descriptor_set",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/quota:descriptor_set",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/quota:golden_files",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/report:descriptor_set",
        "//mixer/tools/codegen/pkg/interfacegen/testdata/report:golden_files",
    ],
    library = ":go_default_library",
)
