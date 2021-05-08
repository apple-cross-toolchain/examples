load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")

package(default_visibility = ["//visibility:public"])

swift_library(
    name = "Kingfisher",
    srcs = glob(
        ["Sources/**/*.swift"],
        exclude = ["Sources/SwiftUI/*.swift"],
    ),
    module_name = "Kingfisher",
)

swift_library(
    name = "KingfisherSwiftUI",
    srcs = glob(["Sources/SwiftUI/*.swift"]),
    module_name = "KingfisherSwiftUI",
    deps = [":Kingfisher"],
)
