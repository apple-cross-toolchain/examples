load("@build_bazel_rules_apple//apple:ios.bzl", "ios_static_framework")

objc_library(
    name = "MBProgressHUD",
    srcs = ["MBProgressHUD.m"],
    hdrs = ["MBProgressHUD.h"],
)

ios_static_framework(
    name = "MBProgressHUDFramework",
    bundle_name = "MBProgressHUD",
    minimum_os_version = "12.0",
    umbrella_header = "MBProgressHUD.h",
    deps = [":MBProgressHUD"],
)
