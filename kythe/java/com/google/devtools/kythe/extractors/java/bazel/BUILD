load("@bazel_skylib//:bzl_library.bzl", "bzl_library")
load("@rules_java//java:defs.bzl", "java_binary")

package(default_visibility = ["//visibility:public"])

java_binary(
    name = "java_extractor",
    srcs = ["JavaExtractor.java"],
    add_exports = [
        "jdk.compiler/com.sun.tools.javac.api",
        "jdk.compiler/com.sun.tools.javac.code",
        "jdk.compiler/com.sun.tools.javac.file",
        "jdk.compiler/com.sun.tools.javac.main",
        "jdk.compiler/com.sun.tools.javac.util",
    ],
    main_class = "com.google.devtools.kythe.extractors.java.bazel.JavaExtractor",
    deps = [
        "//kythe/java/com/google/devtools/kythe/common:flogger",
        "//kythe/java/com/google/devtools/kythe/extractors/java",
        "//kythe/java/com/google/devtools/kythe/extractors/shared",
        "//kythe/java/com/google/devtools/kythe/extractors/shared:file_vnames",
        "//kythe/java/com/google/devtools/kythe/util:json",
        "//kythe/proto:buildinfo_java_proto",
        "//kythe/proto:java_java_proto",
        "//third_party/bazel:extra_actions_base_java_proto",
        "//third_party/guava",
        "@com_google_protobuf//:protobuf_java",
        "@com_google_protobuf//:protobuf_java_util",
        "@io_bazel_files//src/java_tools/buildjar/java/com/google/devtools/build/buildjar:javac_options",
    ],
)

bzl_library(
    name = "aspect_bzl",
    srcs = ["aspect.bzl"],
    deps = [
        "@rules_java//java:rules",
        "@rules_java//java:utils",
    ],
)
