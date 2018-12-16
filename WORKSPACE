load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
# load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

http_archive(
    name = "com_github_tmc_rules_pip",
    strip_prefix = "rules_pip-5b3530ef14d15b7df2b409a33e9deb2ef4414d93",
    url = "https://github.com/tmc/rules_pip/archive/5b3530ef14d15b7df2b409a33e9deb2ef4414d93.zip",
    sha256 = "1b06279dd21631b5454b2277271cae62b296616f46c6f6fbd945c35732775f41",
)
# git_repository(
#     name = "com_github_tmc_rules_pip",
#     commit = "5b3530ef14d15b7df2b409a33e9deb2ef4414d93",
#     remote = "https://github.com/tmc/rules_pip.git",
# )
#load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# local_repository(name = "com_github_tmc_rules_pip", path = "../../apt-itude/rules_pip")

load("@com_github_tmc_rules_pip//rules:dependencies.bzl", "pip_rules_dependencies")

pip_rules_dependencies()

load("@com_github_tmc_rules_pip//rules:repository.bzl", "pip_repository")

pip_repository(
    name = "pip3",
    python_interpreter = "python3",
    requirements = "//:requirements.txt",
)
