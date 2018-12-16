load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

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
