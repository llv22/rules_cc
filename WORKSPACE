workspace(name = "rules_cc")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "bazel_federation",
    sha256 = "0d6893f0d18f417a3324ce7f0ed2e6e5b825d6d5ab42f0f3d7877cb313f36453",
    strip_prefix = "bazel-federation-6ad33bc586701e9836a2bf4432c7aff1235b04d2",
    type = "zip",
    url = "https://github.com/bazelbuild/bazel-federation/archive/6ad33bc586701e9836a2bf4432c7aff1235b04d2.zip",  # 2019-09-30
)

load("@bazel_federation//:repositories.bzl", "rules_cc_deps")

rules_cc_deps()

load("@bazel_federation//setup:rules_cc.bzl", "rules_cc_setup")

rules_cc_setup()

#
# Dependencies for development of rules_cc itself.
#
load("//:internal_deps.bzl", "rules_cc_internal_deps")

rules_cc_internal_deps()

load("//:internal_setup.bzl", "rules_cc_internal_setup")

rules_cc_internal_setup()

http_archive(
    name = "com_google_googletest",
    sha256 = "9dc9157a9a1551ec7a7e43daea9a694a0bb5fb8bec81235d8a1e6ef64c716dcb",
    strip_prefix = "googletest-release-1.10.0",
    urls = [
        "https://mirror.bazel.build/github.com/google/googletest/archive/release-1.10.0.tar.gz",
        "https://github.com/google/googletest/archive/release-1.10.0.tar.gz",
    ],
)

http_archive(
    name = "rules_proto",
    sha256 = "fb7f1959d2d2bf4d7a1f4f29d650845a9a2303b7879c6792320ba8244910ab01",
    strip_prefix = "rules_proto-3212323502e21b819ac4fbdd455cb227ad0f6394",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/3212323502e21b819ac4fbdd455cb227ad0f6394.tar.gz",
        "https://github.com/bazelbuild/rules_proto/archive/3212323502e21b819ac4fbdd455cb227ad0f6394.tar.gz",
    ],
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")

rules_proto_dependencies()

rules_proto_toolchains()

load("//cc:repositories.bzl", "rules_cc_toolchains")

rules_cc_toolchains()

local_repository(
    name = "test_repo",
    path = "examples/test_cc_shared_library2",
)
