load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_applecross",
    sha256 = "3c6b017792789714323d75f29569239855cfb223ce28768df39a910fe7842863",
    strip_prefix = "rules_applecross-0.0.2",
    url = "https://github.com/apple-cross-toolchain/rules_applecross/archive/refs/tags/0.0.2.tar.gz",
)

http_archive(
    name = "build_bazel_rules_apple",
    patch_args = ["-p1"],
    patches = ["@rules_applecross//third_party:rules_apple.patch"],
    sha256 = "5fed4c90b82006176b28d44d7642f520aa2fb9a32d30e24b22071fabcd24cbeb",
    strip_prefix = "rules_apple-0a67f1bd6c4cb9bd1bee5c51ac8d6632da537310",
    url = "https://github.com/bazelbuild/rules_apple/archive/0a67f1bd6c4cb9bd1bee5c51ac8d6632da537310.tar.gz",
)

load("@build_bazel_rules_apple//apple:repositories.bzl", "apple_rules_dependencies")

apple_rules_dependencies()

load(
    "@rules_applecross//toolchain:apple_cross_toolchain.bzl",
    "apple_cross_toolchain",
)

apple_cross_toolchain(
    name = "apple_cross_toolchain",
    clang_sha256 = "8f50330cfa4c609841e73286a3a056cff95cf55ec04b3f1280d0cd0052e96c2a",
    clang_strip_prefix = "clang+llvm-12.0.0-x86_64-linux-gnu-ubuntu-20.04",
    clang_urls = ["https://github.com/apple-cross-toolchain/ci/releases/download/0.0.6/clang+llvm-12.0.0-x86_64-linux-gnu-ubuntu-20.04-stripped.tar.xz"],
    swift_sha256 = "869edb04a932c9831922541cb354102244ca33be0aa6325d28b0f14ac0a32a4d",
    swift_strip_prefix = "swift-5.3.3-RELEASE-ubuntu20.04",
    swift_urls = ["https://github.com/apple-cross-toolchain/ci/releases/download/0.0.6/swift-5.3.3-RELEASE-ubuntu20.04-stripped.tar.xz"],
    xcode_sha256 = "44221c0f4acd48d7a33ee7e51143433dee94c649cfee44cfff3c7915ac54fdd2",
    xcode_urls = ["https://github.com/apple-cross-toolchain/apple-sdks/releases/download/0.0.4/apple-sdks-xcode-12.4.tar.xz"],
)

load("@apple_cross_toolchain//:repositories.bzl", "apple_cross_toolchain_dependencies")

apple_cross_toolchain_dependencies()

load("@build_bazel_rules_swift//swift:repositories.bzl", "swift_rules_dependencies")

swift_rules_dependencies()

load("@build_bazel_rules_swift//swift:extras.bzl", "swift_rules_extra_dependencies")

swift_rules_extra_dependencies()

# Example repositories

http_archive(
    name = "RedditOS",
    build_file = "//third_party:RedditOS.BUILD",
    patch_args = ["-p1"],
    patches = ["//third_party:RedditOS.patch"],
    sha256 = "905fc46eaaa69374d0515b196786e9af2bc30fbae808c3735ccb95fd558801ad",
    strip_prefix = "RedditOS-d0efbe4b97ee8da6f482d3dc3f23cf43ae3f9b09",
    url = "https://github.com/Dimillian/RedditOS/archive/d0efbe4b97ee8da6f482d3dc3f23cf43ae3f9b09.zip",
)

http_archive(
    name = "KeychainAccess",
    build_file = "//third_party:KeychainAccess.BUILD",
    sha256 = "60220101941a8f49822be0d0856c01e65c20b3cfee9d7aa80c52649cff37ff0e",
    strip_prefix = "KeychainAccess-4.2.2",
    url = "https://github.com/kishikawakatsumi/KeychainAccess/archive/refs/tags/v4.2.2.zip",
)

http_archive(
    name = "Kingfisher",
    build_file = "//third_party:Kingfisher.BUILD",
    sha256 = "70677c1a1386c708d161b23b7d46135074d31d47d60cf1858743eb7b4007f634",
    strip_prefix = "Kingfisher-5.15.8",
    url = "https://github.com/onevcat/Kingfisher/archive/refs/tags/5.15.8.zip",
)

http_archive(
    name = "MBProgressHUD",
    build_file = "//third_party:MBProgressHUD.BUILD",
    sha256 = "6533ca3bd481091979d3ec2db140c252d4bcc470276b16c806910f04276ae798",
    strip_prefix = "MBProgressHUD-c843e4c86d320a11552898646effa8000042ab16",
    url = "https://github.com/jdg/MBProgressHUD/archive/c843e4c86d320a11552898646effa8000042ab16.zip",
)
