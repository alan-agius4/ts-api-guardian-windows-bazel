load("@angular//tools/ts-api-guardian:index.bzl", "ts_api_guardian_test")

[ts_api_guardian_test(
    name = "%s_%s_%sapi" % (
        bundle[0],
        bundle[1],
        bundle[2].replace("src/", "").replace("index", "").replace("/", "_"),
    ),
    actual = "packages/%s/%s/npm_package/%s.d.ts" % (
        bundle[0],
        bundle[1],
        bundle[2],
    ),
    data = glob([
        "%s/%s/**/*.d.ts" % (
            bundle[0],
            bundle[1],
        ),
    ]) + [
        "//packages/%s/%s:npm_package" % (
            bundle[0],
            bundle[1],
        ),
    ],
    golden = "etc/api/%s/%s/%s.d.ts" % (
        bundle[0],
        bundle[1],
        bundle[2],
    ),
    allow_module_identifiers = [
        "fs",
        "ts",
        "Symbol",
    ],
) for bundle in [b[:-len(".d.ts")].split("/", 2) for b in glob(
    ["**/*.d.ts"],
)]]
