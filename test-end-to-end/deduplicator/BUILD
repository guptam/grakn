load("//dependencies/tools/checkstyle:checkstyle.bzl", "checkstyle_test")

java_test(
    name = "attribute-deduplicator-e2e",
    test_class = "grakn.core.deduplicator.AttributeDeduplicatorE2E",
    srcs = ["AttributeDeduplicatorE2E.java", "AttributeDeduplicatorE2EConstants.java"],
    deps = [
        # Internal dependencies
        "//client-java:client-java",
        "//common:common",
        "//concept:concept",
        "//server:server",

        # External dependencies from @graknlabs
        "@graknlabs_graql//java:graql",

        # External dependencies from Maven
        "//dependencies/maven/artifacts/commons-io:commons-io",
        "//dependencies/maven/artifacts/org/rocksdb:rocksdbjni",
        "//dependencies/maven/artifacts/org/zeroturnaround:zt-exec",
        "//dependencies/maven/artifacts/org/hamcrest:hamcrest-library",
        "//dependencies/maven/artifacts/org/slf4j:slf4j-api"
    ],
    data = ["//:distribution"],
    classpath_resources = ["//test-integration/resources:logback-test"]
)

checkstyle_test(
    name = "checkstyle",
    targets = [":attribute-deduplicator-e2e"],
)
