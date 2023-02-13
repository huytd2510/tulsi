load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# TODO: Remove once https://github.com/bazelbuild/bazel-skylib/pull/307 is merged and patch is removed from rules_apple
http_archive(
    name = "io_bazel_stardoc",
    sha256 = "f89bda7b6b696c777b5cf0ba66c80d5aa97a6701977d43789a9aee319eef71e8",
    strip_prefix = "stardoc-d93ee5347e2d9c225ad315094507e018364d5a67",
    url = "https://github.com/bazelbuild/stardoc/archive/d93ee5347e2d9c225ad315094507e018364d5a67.tar.gz",
)

# Rules Swift

RULES_SWIFT_VERSION = "vinone-0.18.1"

RULES_SWIFT_SHA = "a065a2aabffc6e8ddee6988d407c8a2ca46a8c61c78c96d6ff07601ee5427b26"

http_archive(
    name = "build_bazel_rules_swift",
    sha256 = RULES_SWIFT_SHA,
    strip_prefix = "rules_swift-%s" % RULES_SWIFT_VERSION,
    url = "https://github.com/kevinnguyenhoang91/rules_swift/archive/%s.tar.gz" % RULES_SWIFT_VERSION,
)

# Apple Bazel Rules Dependency
RULES_APPLE_VERSION = "vinone-0.21.2.2"
RULES_APPLE_SHA = "e8fccef2e28e2205308255847b98aa5e4ffb0244122eb80c2dfaa565ae1ce476"
http_archive(
    name = "build_bazel_rules_apple",
    sha256 = RULES_APPLE_SHA,
    strip_prefix = "rules_apple-vinone-0.21.2.2",
    urls = ["https://github.com/diesel-engineer/rules_apple/archive/%s.tar.gz" % RULES_APPLE_VERSION],
)

load(
    "@build_bazel_rules_apple//apple:repositories.bzl",
    "apple_rules_dependencies",
)

apple_rules_dependencies()

# @build_bazel_rule_swift is already defined via apple_rules_dependencies above.
# This helps ensure that Tulsi, rules_apple, etc. are using the same versions.
load(
    "@build_bazel_rules_swift//swift:repositories.bzl",
    "swift_rules_dependencies",
)

swift_rules_dependencies()

# @build_bazel_apple_support is already defined via apple_rules_dependencies above.
# This helps ensure that Tulsi, rules_apple, etc. are using the same versions.
load(
    "@build_bazel_apple_support//lib:repositories.bzl",
    "apple_support_dependencies",
)

apple_support_dependencies()
