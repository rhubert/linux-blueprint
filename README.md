# Bob GNU/Linux blueprint

This project serves as a blueprint to build a GNU/Linux system with the
[Bob Build Tool](https://bobbuildtool.dev/). It can be used as a starting
point for embedded Linux projects.

This repository uses the [basement](https://github.com/BobBuildTool/basement)
and [basement-gnu-linux](https://github.com/BobBuildTool/basement-gnu-linux)
recipe layers. They provide common recipes for Linux, busybox, cross compilers
and standard build systems.

For more information about recipe layers and Bob's usage in general, see [its
documentation](https://bob-build-tool.readthedocs.io/en/latest/index.html).

# Prerequisites

* A `x86_64` system with the regular development tools installed (GCC, make,
  Perl, ...)
* [Bob Build Tool](https://github.com/BobBuildTool/bob)
* Patience :coffee:

To actually run the built images, you'll also need Qemu.

# How to build

Clone the recipes and fetch required layers:

    $ git clone https://github.com/BobBuildTool/linux-blueprint.git
    $ cd linux-blueprint
    $ bob layers update

Using `bob ls`, you can view the top-level recipes that can be built:

    $ bob ls
    amd64-glibc-busybox-wayland
    amd64-glibc-busybox-x11
    amd64-glibc-systemd-wayland
    amd64-glibc-systemd-x11
    amd64-uclibc

Execute the following command to build the first image:

    $ bob dev amd64-glibc-busybox-wayland -j

# How to use

Every image has a `run.sh` that can be executed to run the built image in Qemu:

    $ dev/dist/amd64-glibc-busybox-wayland/1/workspace/run.sh

The script starts Qemu to run the image in a virtual machine.

# Contributions

Contributions are welcome in form of feedback, bug reports and code. If you want
to contribute in the form of code but are unsure about how to do things exactly,
feel free to open up a pull request and ask for help.
