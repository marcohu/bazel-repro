workspace(name="bazel")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "antlr3_runtimes",
    sha256 = "d4f7d3c38c5523f8009ff37528e5797c81adb454be6acc9af507cfcb41f2016f",
    strip_prefix = "antlr3-master",
    urls = ["https://github.com/ibre5041/antlr3/archive/master.tar.gz"],
    build_file = "//:antlr.BUILD",
    #workspace_file = "@//:antlr.WORKSPACE",
)
