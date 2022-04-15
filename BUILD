genrule(
    name = "unsound",
    srcs = [],
    outs = ["out"],
    cmd = """
        echo $(CC) > $@
    """,
    toolchains = ["@bazel_tools//tools/cpp:current_cc_toolchain"],
)
