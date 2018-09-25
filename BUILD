# Marker file indicating this directory is a Bazel package

package(default_visibility = ["//visibility:public"])

exports_files([
    "tsconfig.json",
    "index.js"
])

filegroup(
    name = "node_modules",
    srcs = glob(
        [
            "node_modules/**/*.js",
            "node_modules/**/*.json",
            "node_modules/**/*.d.ts",
        ],
    ) + glob(["node_modules/.bin/*"]),
)
# @external_end
