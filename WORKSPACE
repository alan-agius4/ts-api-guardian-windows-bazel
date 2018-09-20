workspace(name = "testing_guardian")

# We get Buildifier from here.
http_archive(
    name = "com_github_bazelbuild_buildtools",
    url = "https://github.com/bazelbuild/buildtools/archive/0.15.0.zip",
    strip_prefix = "buildtools-0.15.0",
    sha256 = "76d1837a86fa6ef5b4a07438f8489f00bfa1b841e5643b618e01232ba884b1fe",
)

load("@com_github_bazelbuild_buildtools//buildifier:deps.bzl", "buildifier_dependencies")
buildifier_dependencies()

# The Go toolchain is used for Buildifier.
# rules_typescript_dependencies() also tries to load it but we add it explicitely so we
# don't have hidden dependencies. 
# This also means we need to load it before rules_typescript_dependencies().
http_archive(
    name = "io_bazel_rules_go",
    url = "https://github.com/bazelbuild/rules_go/archive/0.14.0.zip",
    strip_prefix = "rules_go-0.14.0",
    sha256 = "9bd7c2743f014e4e112b671098ba1da6aec036fe07093b10ca39a9f81ec5cc33",
)

load("@io_bazel_rules_go//go:def.bzl", "go_register_toolchains", "go_rules_dependencies")
go_rules_dependencies()
go_register_toolchains()

# We need a minimum of this version to include https://github.com/bazelbuild/rules_nodejs/pull/281.
http_archive(
    name = "build_bazel_rules_nodejs",
    url = "https://github.com/bazelbuild/rules_nodejs/archive/0.12.4.zip",
    strip_prefix = "rules_nodejs-0.12.4",
    sha256 = "c482700e032b4df60425cb9a6f8f28152fb1c4c947a9d61e6132fc59ce332b16",
)

# Load the TypeScript rules, its dependencies, and setup the workspace.
http_archive(
    name = "build_bazel_rules_typescript",
    url = "https://github.com/bazelbuild/rules_typescript/archive/0.16.2.zip",
    strip_prefix = "rules_typescript-0.16.2",
    sha256 = "31601b777840fbf600dbd1893ade0d1de37166e7ba52b90735b107cfb67e38c7",
)

load("@build_bazel_rules_typescript//:package.bzl", "rules_typescript_dependencies")
# build_bazel_rules_nodejs is loaded transitively through rules_typescript_dependencies.
rules_typescript_dependencies()

load("@build_bazel_rules_typescript//:defs.bzl", "ts_setup_workspace")
ts_setup_workspace()

# Load the nodejs dependencies, check minimum Bazel version, and define the local node_modules.
load("@build_bazel_rules_nodejs//:package.bzl", "rules_nodejs_dependencies")
rules_nodejs_dependencies()

# TS API Guardian resides in Angular
http_archive(
    name = "angular",
    url = "https://github.com/angular/angular/archive/9d4b81bb8d4137a695fc3c5cac594b90e088928e.zip",
    strip_prefix = "angular-9d4b81bb8d4137a695fc3c5cac594b90e088928e",
    sha256 = "3c09a2b358bb6d85133b6cccac613a4f54b8d096252dcf171327611d51a60c02",
)

load("@angular//:index.bzl", "ng_setup_workspace")
ng_setup_workspace()

load("@build_bazel_rules_nodejs//:defs.bzl", "check_bazel_version", "node_repositories")
check_bazel_version("0.17.0")
node_repositories(
    package_json = ["//:package.json"], 
    preserve_symlinks = True,
    node_version = "10.3.0",
    yarn_version = "1.6.0",
)
