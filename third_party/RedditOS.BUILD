load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")
load(
    "@build_bazel_rules_apple//apple:macos.bzl",
    "macos_application",
)
load(
    "@build_bazel_rules_apple//apple:versioning.bzl",
    "apple_bundle_version",
)

package(default_visibility = ["//visibility:public"])

swift_library(
    name = "Main",
    srcs = glob(["RedditOs/**/*.swift"]),
    data = glob(
        [
            "RedditOs/Assets.xcassets/**",
        ],
        exclude = ["RedditOs/Assets.xcassets/AppIcon.appiconset/**"],
    ),
    linkopts = [
        "-Wl,-framework,AVKit",
        "-Wl,-framework,SwiftUI",
    ],
    module_name = "RedditOs",
    deps = [
        ":Backend",
        ":UI",
        "@Kingfisher//:KingfisherSwiftUI",
    ],
)

swift_library(
    name = "UI",
    srcs = glob(["Packages/UI/Sources/UI/**/*.swift"]),
    module_name = "UI",
)

swift_library(
    name = "Backend",
    srcs = glob(["Packages/Backend/Sources/Backend/**/*.swift"]),
    module_name = "Backend",
    deps = [
        "@KeychainAccess",
    ],
)

apple_bundle_version(
    name = "Version",
    build_version = "1.0",
)

macos_application(
    name = "Curiosity",
    app_icons = glob(["RedditOs/Assets.xcassets/AppIcon.appiconset/**"]),
    bundle_id = "com.thomasricouard.curiosity",
    infoplists = [":RedditOs/Info.plist"],
    minimum_os_version = "11.0",
    version = ":Version",
    deps = [":Main"],
)
