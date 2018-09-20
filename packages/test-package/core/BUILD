# Copyright Google Inc. All Rights Reserved.
#
# Use of this source code is governed by an MIT-style license that can be
# found in the LICENSE file at https://angular.io/license

licenses(["notice"])  # MIT

load("@build_bazel_rules_typescript//:defs.bzl", "ts_library")
load("@build_bazel_rules_nodejs//:defs.bzl", "npm_package")

package(default_visibility = ["//visibility:public"])

ts_library(
    name = "core",
    srcs = glob(
        include = ["index.ts"],
    ),
    module_name = "test-package/core",
    module_root = "index.d.ts",
)

npm_package(
    name = "npm_package",
    deps = [
        ":core",
    ],
)
