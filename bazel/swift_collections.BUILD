# swift-collections 1.1.6 as `_FoundationCollections`: the four libraries
# FoundationEssentials uses (DequeModule, OrderedCollections, _RopeModule and
# the internal utilities they share) compiled into one module, as the Swift
# toolchain's CMake build does with COLLECTIONS_FOUNDATION_TOOLCHAIN_MODULE.
# Only FoundationEssentials may import it (-allowable-client).

load("@rules_swift//swift:swift.bzl", "swift_library")

swift_library(
    name = "_FoundationCollections",
    srcs = glob([
        "Sources/DequeModule/**/*.swift",
        "Sources/OrderedCollections/**/*.swift",
        "Sources/RopeModule/**/*.swift",
        "Sources/InternalCollectionsUtilities/**/*.swift",
    ]),
    copts = [
        "-DCOLLECTIONS_SINGLE_MODULE",
        "-Xfrontend",
        "-allowable-client",
        "-Xfrontend",
        "FoundationEssentials",
    ],
    module_name = "_FoundationCollections",
    visibility = ["//visibility:public"],
)
