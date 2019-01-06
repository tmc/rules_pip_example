load("@com_github_tmc_rules_pip//rules:compile.bzl", "compile_pip_requirements")
load("@com_github_tmc_rules_pip//tools/pytest:rules.bzl", "pytest_test")
load("@io_bazel_rules_docker//python3:image.bzl", "py3_image")

# BUILD
compile_pip_requirements(
    name = "compile_requirements",
    python_interpreter = "python3",
    requirements_in = "//:requirements.in",
    requirements_txt = "requirements.txt",
    header = "# This file was generated. Do not edit.",
)

py_binary(
    name = "hello_world",
    srcs = ["hello-world.py"],
    deps = [ "@pip3//httplib2" ],
    main = "hello-world.py",
)

pytest_test(
    name = "httplib2_test",
    src = "httplib2_test.py",
    deps = [ "@pip3//httplib2" ],
)

pytest_test(
    name = "pyyaml_test",
    src = "pyyaml_test.py",
    deps = [ "@pip3//pyyaml" ],
)

py3_image(
    name = "hello_world_image",
    srcs = ["hello-world.py"],
    deps = [ "@pip3//httplib2" ],
    main = "hello-world.py",
    stamp = True,
)
