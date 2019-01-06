load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "bazel_skylib",
    remote = "https://github.com/bazelbuild/bazel-skylib.git",
    tag = "0.6.0",  # change this to use a different release
)
http_archive(
    name = "com_github_tmc_rules_pip",
    strip_prefix = "rules_pip-7e1d89801e5c87d0f08dbed702e338c1cc9c925b",
    url = "https://github.com/tmc/rules_pip/archive/7e1d89801e5c87d0f08dbed702e338c1cc9c925b.zip",
    sha256 = "dbd9eff76e2cbb5fa4f9a827f7ab8c64dbbd86d1d2c0b12d8393aa552db42693",
)
#local_repository(name = "com_github_tmc_rules_pip", path = "../../tmc/rules_pip")

load("@com_github_tmc_rules_pip//rules:dependencies.bzl", "pip_rules_dependencies")

pip_rules_dependencies()

load("@com_github_tmc_rules_pip//rules:repository.bzl", "pip_repository")

pip_repository(
    name = "pip3",
    python_interpreter = "python3",
    requirements = "//:requirements.txt",
)

# begin rules_docker
http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "c0e9d27e6ca307e4ac0122d3dd1df001b9824373fb6fb8627cd2371068e51fef",
    strip_prefix = "rules_docker-0.6.0",
    urls = ["https://github.com/bazelbuild/rules_docker/archive/v0.6.0.tar.gz"],
)
load(
    "@io_bazel_rules_docker//python3:image.bzl",
    _py3_image_repos = "repositories",
)
_py3_image_repos()
# end rules_docker
