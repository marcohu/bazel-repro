workspace(name="maven_property")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_jar", "http_archive")

RULES_JVM_EXTERNAL_TAG = "3.0"
RULES_JVM_EXTERNAL_SHA = "62133c125bf4109dfd9d2af64830208356ce4ef8b165a6ef15bbff7460b35c3a"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "org.eclipse.platform:org.eclipse.ui.workbench:3.108.3",
        "org.eclipse.platform:org.eclipse.jface:3.12.2",
    ],
    repositories = [
        "https://repo1.maven.org/maven2",
#        "https://jcenter.bintray.com/",
    ],
    strict_visibility = True,
)
