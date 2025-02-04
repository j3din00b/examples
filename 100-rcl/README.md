# Easy build matrixing with [RCL](https://rcl-lang.org/)

[RCL](https://rcl-lang.org/) is a next-gen configuration language built in Rust which in this context can be used for easy matrixed recipe generation and image building through its simple way of generating configuration files. RCL is a superset of JSON and functions similarly to Jsonnet and Nix, but has a much better syntax and user experience.

This example showcases how to use RCL to generate a bunch recipes and build them all concurrently using with the GitHub Actions build matrix. The build matrix is automatically generated from the output of the `rcl build` command, and the logic of that generation might have to be adjusted to future RCL updates.

- See [recipes.rcl](./recipes.rcl) for the RCL configuration.
- See [build.yml](./build.yml) for the GitHub Actions workflow.

When working with a third-party configuration language, it is recommended to use the importing feature of the language instead of `from-file`, such that you can leave the `recipes/` directory completely empty or even uncreated. If you still want to use `from-file`, remember that the paths are not relative to the `.rcl` file, but to the `recipes/` directory.   
See RCL's [documentation for file imports](https://docs.ruuda.nl/rcl/imports/).