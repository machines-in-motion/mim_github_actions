mim_github_actions
------------------

Contains a collections of github actions for th CI of the packages from
the
[machines-in-motion](https://github.com/machines-in-motion)
and the
[open-dynamic-robot-initiative](https://github.com/open-dynamic-robot-initiative)

This package contains so far actions for:
- Setting up the code-base dependencies from apt and pip on Ubuntu18.04.
- Setting up the code-base dependencies from apt and pip on Ubuntu20.04.
- Cloning and building dependencies from source.
- Building and running CTest.

### Usage

#### Demos/Examples

Here are samples of code to use the actions present in this package.

##### Setting up the code-base dependencies from apt and pip on Ubuntu18.04.

```yml
- name: Setup Ubuntu18.04.
  uses: machines-in-motion/mim_github_actions/setup_ubuntu18_04@main
```

##### Setting up the code-base dependencies from apt and pip on Ubuntu20.04.

```yml
- name: Setup Ubuntu20.04.
  uses: machines-in-motion/mim_github_actions/setup_ubuntu20_04@main
```

##### Cloning and building dependencies from source.

```yml
- name: Clone dependencies and build them.
  uses: machines-in-motion/mim_github_actions/treep_clone_and_build@main
  with:
    treep_configurations: >
      "git@github.com:orga_name1/treep_orga1.git;
       git@github.com:orga_name2/treep_orga2.git"
    projects_or_repos: "PROJECT1;PROJECT2;repository1;repository2"
```

##### Building and running CTest.

```yml
- name: Build and test the current package using ctest.
  uses: machines-in-motion/mim_github_actions/cmake_build_and_ctest@main
```

#### Full example

In this example we also used a private ssh key to clone the additional sources
we needed:

https://github.com/machines-in-motion/package_template/blob/master/.github/workflows/ci_ubuntu_18_04_release.yml


### License and Copyrights

License BSD-3-Clause
Copyright (c) 2021, New York University and Max Planck Gesellschaft.
