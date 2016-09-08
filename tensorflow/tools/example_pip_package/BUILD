package(default_visibility = ["//visibility:public"])

load(":tensorflow.bzl", "tf_py_wrap_cc")
export_files = (["swig.bat"])


genrule(
    name = "pywrap_example_pyd_file",
    outs = ["_pywrap_example.pyd"],
    srcs = [":_pywrap_example.dll"],
    cmd = "cp $< $@",
)

tf_py_wrap_cc(
    name = "pywrap_example",
    srcs = ["example.i"],
    deps = [
        ":example_lib",
    ],
)


py_binary(
    name = "simple_console",
    srcs = ["simple_console.py"],
    deps = [":pywrap_example"],
    data = [":pywrap_example_pyd_file"],
)

cc_library(
    name = "example_lib",
    srcs = ["example_lib.c"],
    hdrs = [
        "example_lib.h",
    ],
)

filegroup(
    name = "swig",
    srcs = ["swig.bat"],
)

