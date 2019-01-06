# rules_pip_example

This demonstrates the use of [rules_pip](https://github.com/tmc/rules_pip).

## Targets
- **compile_requirements** -  `bazel run //:compile_requirements` - regenerates requirements.txt
- **hello_world** -  `bazel run //:hello_world` - says hello, prints python version
- **hello_world_image** -  `bazel run //:hello_world_image` - says hello, prints python version (from built docker image)
