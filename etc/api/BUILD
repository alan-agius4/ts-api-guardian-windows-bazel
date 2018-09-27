
load("@build_bazel_rules_nodejs//:defs.bzl", "nodejs_test")

nodejs_test(
    name = "accept",
    data = glob([
        "test-package/core/*.d.ts"
    ]) + [
        "index.js",
        "//packages/test-package/core:npm_package"
    ],
    entry_point = "testing_guardian/etc/api/index.js",
    templated_args = [
        "--in",
        "$(rlocation testing_guardian/packages/test-package/core/npm_package)",
        "--out",
        "$(rlocation testing_guardian/etc/api/test-package/core/index.d.ts)"
    ],
)
