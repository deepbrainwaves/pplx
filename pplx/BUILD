
cc_library(
    name = "pplx",
    srcs = ["cpprest_compat.h", "pplxconv.h", "pplxinterface.h", "pplxtasks.h", "stdafx.h",
            "pplxcancellation_token.h", "pplx.cpp", "threadpool.cpp", "threadpool.h"]
    + select({
        "//conditions:default"   : ["pplxlinux.cpp", "pplxlinux.h"],
        "@bazel_tools//src/conditions:darwin"  : ["pplxapple.cpp", "pplxlinux.h"],
        "@bazel_tools//src/conditions:windows" : ["pplxwin.cpp",   "pplxwin.h"],
    }),
    hdrs = glob(["pplx/**/*.h"]),
    copts = ["-std=c++17"],
#    linkopts = ["-lboost_system", "-lcrypto", "-lssl"],
    deps = [
        "//third_party:boost",
        "//third_party:crypto",
        "//third_party:libssl",
    ],
)
