load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

### LLVM ###
http_archive(
    name = "com_grail_bazel_toolchain",
    sha256 = "6c0b44a123e701c0749344bf5d4154725a9e74083b8eb742da20252a6781a0f4",
    strip_prefix = "bazel-toolchain-d2269a47d87d4dd5ac730c0ff976973383a45106",
    urls = ["https://github.com/grailbio/bazel-toolchain/archive/d2269a47d87d4dd5ac730c0ff976973383a45106.tar.gz"],
)

load("@com_grail_bazel_toolchain//toolchain:deps.bzl", "bazel_toolchain_dependencies")

bazel_toolchain_dependencies()

load("@com_grail_bazel_toolchain//toolchain:rules.bzl", "llvm_toolchain")

# The version should be synced to the output of `rustc -vV`.
# TODO(david): One day we probably need to build our own copies of LLVM and Rust to sync the versions.
llvm_toolchain(
    name = "llvm_toolchain",
    llvm_version = "14.0.0",
    sha256 = {
        "ubuntu-20.04-x86_64": "61582215dafafb7b576ea30cc136be92c877ba1f1c31ddbbd372d6d65622fef5",
    },
    strip_prefix = {
        "ubuntu-20.04-x86_64": "clang+llvm-14.0.0-x86_64-linux-gnu-ubuntu-18.04",
    },
    urls = {
        "ubuntu-20.04-x86_64": ["https://github.com/llvm/llvm-project/releases/download/llvmorg-14.0.0/clang+llvm-14.0.0-x86_64-linux-gnu-ubuntu-18.04.tar.xz"],
    },
)
### LLVM ###